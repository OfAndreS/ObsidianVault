
---

Aplicar a técnica de aumento de dados pode introduzir ruído na base de treinamento, dependendo da natureza das informações analisadas. Em um conjunto de dados do alfabeto, por exemplo, aplicar uma inversão vertical ou rotação de 180º na letra "W" fará com que ela seja confundida com a letra "M". Portanto, para cada coleção de dados, os métodos de transformação devem ser escolhidos individualmente, respeitando o contexto do problema.

**Transformações Geométricas e Espaciais**

- RandomHorizontalFlip
- RandomRotation
- RandomResizedCrop

**Ajustes de Cor e Iluminação**

- ColorJitter
- RandomGrayscale
- GaussianBlur

**Oclusão e Regularização**

- RandomErasing
- CutMix
- MixUp

**Aumento Automático (Auto-Augmentation)**

- AutoAugment
- RandAugment
- AugMix

**Transformações de Áudio**

- TimeMasking
- FrequencyMasking
- TimeStretch