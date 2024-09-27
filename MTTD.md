# Calculo de MTTD

Teniendo en cuenta la información proporcionada sobre `Mean Time to Detect (MTTD)`, para calcular el tiempo promedio que me tomaría para detectar
un problema o error en el sistema utilizando mis casos de prueba a manera hipotética. Por ejemplo, si
de los 30 casos de prueba que analicé, planeé, diseñé y ejecute, 16 casos tuvieron errores, por lo tanto, calculo en
un tiempo X el MTTD.

- De acuerdo al documento para calcular el MTTD se realiza sumando el tiempo total que tomó detectar todos los errores y dividiéndolo por el número total de errores detectados.
- **Fórmula**: MTTD = Σ Tiempo para detectar errores / Número total de errores detectados

### Cálculo hipotético:

A continuación, presento un ejemplo de cómo podría distribuir el tiempo de detección de errores, asumiendo un tiempo promedio de 15 minutos por error:

- **Total de errores detectados (hipotético)**: 10 errores
- **Tiempo total para detectar los errores**: 150 minutos (10 errores × 15 minutos por error)
- **MTTD (Tiempo promedio de detección)**: 15 minutos por error
- **Capacidad diaria de detección**: Teniendo en cuenta la formula `(480 minutos ÷ 15 minutos por error)`, en mi jornada laboral de 8 horas (480 minutos), se podrían detectar `**32 errores**`.

`Nota`: Este ejemplo es hipotético y está enfocado en mostrar cómo se podría distribuir mi tiempo, sin embargo, el MTTD puede variar en función de diversos factores como la complejidad de los casos de prueba o el tamaño de las historias de usuario.
