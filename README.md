# MLX90640-With-STM32
MLX90640 is a fully calibrated 32x24 pixels thermal IR array sensor.

## MLX90640 with STM32 SWI2C 
* SDA_PIN:PB7
* SCL_PIN:PB6

The data will printf on UASRT1 with 115200 buad rate like the blow picture!

![](https://github.com/imliubo/MLX90640-With-STM32/blob/master/image/MLX90640_STM32_HAL_SWI2C.png)

## MLX90640 with STM32 HWI2C 
* SDA_PIN:PB7
* SCL_PIN:PB6
* I2C Clock Speed: 400000Hz
* RefreshRate: <=16Hz (>=32Hz Fail...)

The data will printf on UASRT1 with 115200 buad rate like the blow picture!

![](https://github.com/imliubo/MLX90640-With-STM32/blob/master/image/MLX90640_STM32_HAL_HWI2C.png)

# Merge with this officail version 
https://github.com/melexis/mlx90640-library

# Tested
```
#define ARD_D15_STMOD_I2C2_SCL_Pin GPIO_PIN_4
#define ARD_D15_STMOD_I2C2_SCL_GPIO_Port GPIOH
#define ARD_D14_STMOD_I2C2_SDA_Pin GPIO_PIN_5
#define ARD_D14_STMOD_I2C2_SDA_GPIO_Port GPIOH

hi2c2.Instance = I2C2;
hi2c2.Init.Timing = 0x00500B19;
hi2c2.Init.OwnAddress1 = 0;
hi2c2.Init.AddressingMode = I2C_ADDRESSINGMODE_7BIT;
hi2c2.Init.DualAddressMode = I2C_DUALADDRESS_DISABLE;
hi2c2.Init.OwnAddress2 = 0;
hi2c2.Init.OwnAddress2Masks = I2C_OA2_NOMASK;
hi2c2.Init.GeneralCallMode = I2C_GENERALCALL_DISABLE;
hi2c2.Init.NoStretchMode = I2C_NOSTRETCH_DISABLE;

* I2C Clock Speed: 400000Hz
* RefreshRate: 2~64 Success , 1 and 0.5 not yet test
```

# TODO 
```
int MLX90640_I2CGeneralReset(void); // need to test
int MLX90640_TriggerMeasurement(uint8_t slaveAddr); // no complete
```
