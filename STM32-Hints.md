# STM32 Hints!

+ ## Get STLink V2 to upload code when it seems to be hanging due to an interrupt or sleep conflict
  Bring the BOOT0 pin (pin 1) high. While keeping it high, momentarily ground the reset (NRST) pin (pin 4).
  Then, while BOOT0 is still high, initialize the upload. Release the BOOT0 pin. If the code does not run after
  the upload, then momentarily ground the reset (NRST) pin after releasing the BOOT0 pin. It should work!

+ ## Modulate or Break a PWM Signal to a High or Low State
  After you have set up a PWM output signal, change the OCxM bits in the CCMRx register to force the output high or low.<br>

### From the Reference Manual:
![image](https://github.com/EZdenki/MyStuff/assets/142701437/da949f79-dee3-443e-9533-3375711879e0)

### Sample Code:
<pre>
int
main( void )
{
  // -----------------------------------------------------------------------------------------
  // Set up PWM output for LED on pin 14, PB1/TIM14_CH1(AF0) for 10 Hz, 50% duty output
  // -----------------------------------------------------------------------------------------
  RCC->AHBENR  |= RCC_AHBENR_GPIOBEN;      // Enable GPIO Port B
  RCC->APB1ENR |= RCC_APB1ENR_TIM14EN;     // Enable TIM14
  GPIOB->MODER |= GPIO_MODER_MODER1_1;     // Set GPIO B1 as alternate function
  // Don't need to set GPIOA->AFR[0] because AF0 is default alternate function
  TIM14->CCMR1 |= (0b110 << TIM_CCMR1_OC1M_Pos);  // TIM14/Ch1 output compare PWM mode 1
  TIM14->PSC    = 8000;                    // Set prescaler for 1 ms tick
  TIM14->ARR    = 100;                     // Set Auto Reload Register for 100 ms period (10 Hz)
  TIM14->CCR1   = 50;                      // Set duty cycle to 50%
  TIM14->CCER  |= TIM_CCER_CC1E;           // Enable (start) the timer capture to update the output
  TIM14->CR1   |= TIM_CR1_CEN;             // Start the timer!

  // -----------------------------------------------------------------------------------------
  // Modulate the 10 Hz signal for 250 ms ON and 750 ms OFF.
  // -----------------------------------------------------------------------------------------
  while( 1 )
  {
    for( uint32_t x=0; x<154e3; x++ ) ;               // Allow 10 Hz PWM output for approx. 250 ms  
    
    TIM14->CNT = 0;                                   // Reset timer counter
    <b>TIM14->CCMR1 &= ~(0b111 << TIM_CCMR1_OC1M_Pos);</b>   // Clear OC1M bits
    <b>TIM14->CCMR1 |=  (0b100 << TIM_CCMR1_OC1M_Pos);</b>   // Force output compare channel 1 to low state.
                                                      // Change to 0b101 to force output to a high state.
    for( uint32_t x=0; x<463e3; x++ ) ;               // Keep output low for approx. 750 ms

    TIM14->CNT = 0;                                   // Reset timer counter
    <b>TIM14->CCMR1 &= ~(0b111 << TIM_CCMR1_OC1M_Pos);</b>   // Clear OC1M bits
    <b>TIM14->CCMR1 |=  (0b110 << TIM_CCMR1_OC1M_Pos);</b>   // Resume 10 Hz PWM on output compare channel 1
  }
}
</PRE>
