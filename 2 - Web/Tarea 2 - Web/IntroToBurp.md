#notas_hacking #web
# Reto
## Descripción
Try [here](http://titan.picoctf.net:54415/) to find the flag
## Solución

```bash
Cookie: session=.eJw9jEsKAjEQBe-StYvE_L1MaKe7UZxJhnwQEe9uhMHdq4J6b7Hc-0tcRBMnsbTKqZcH5SmsRsfgQ0RQVjkwBpWNUpqgCWPwHpgDspsdj3VNGTY6fkrf53JaRXmeuENrz1JxOvXDW8mU8tiuVA81GtV___kCrHUr3A.aOH6Ww.hNeChYdMahi4DISui_8zp6U7hko
Connection: keep-alive

otp=1
```
cambio `otp=1` para que falle a `otp1=1`
`Welcome, s you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_b3fa4f1a}`
## Notas

## Referencias
