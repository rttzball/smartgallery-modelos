# smartgallery-modelos

Modelos de IA que o Smart Gallery baixa para a busca por frase e para sugerir categorias. Este repositório só hospeda os arquivos, na
[Release `xlm-laion5b-s13b-b90k-opset18`](https://github.com/rttzball/smartgallery-modelos/releases/tag/xlm-laion5b-s13b-b90k-opset18).
Não há código do app aqui.

Models the Smart Gallery app downloads for text-to-image search. This repository only hosts the files.

## Arquivos

| Arquivo | Bytes | SHA-256 |
|---|---|---|
| `visual.onnx` | 351781049 | `30528bae840f90e838e42fa9c5468dc35153d7f936eb44d78433bf4a5e53aeaa` |
| `textual_int8.onnx` | 278991512 | `e4407c069139ae29714fa218d712d78ddf290849b37e7e76812810e8c9fc8305` |
| `sentencepiece.bpe.model` | 5069051 | `cfc8146abe2a0488e9e2a0c56de7952f7c11ab059eca145a0a727afce0db2865` |

O app confere o SHA-256 depois de baixar e recusa o arquivo que não bater.

## Origem

- Modelo OpenCLIP `xlm-roberta-base-ViT-B-32`, pesos `laion5b_s13b_b90k`, treinado no LAION-5B
  ([OpenCLIP](https://github.com/mlfoundations/open_clip), licença MIT).
- Torre de texto e vocabulário do XLM-RoBERTa base ([FacebookAI/xlm-roberta-base](https://huggingface.co/FacebookAI/xlm-roberta-base), licença MIT).
  `sentencepiece.bpe.model` é o vocabulário original desse modelo.
- `visual.onnx`: torre de imagem exportada para ONNX opset 18, em float32.
- `textual_int8.onnx`: torre de texto exportada para ONNX opset 18 e quantizada para int8.
- A exportação foi feita para o Smart Gallery. Os pesos não foram retreinados nem alterados, além da quantização da torre de texto.

## Licença

MIT, a mesma dos modelos de origem. Veja [LICENSE](LICENSE) e as licenças dos projetos acima.
Os dados de treino (LAION-5B) têm termos próprios, descritos pelo LAION.
