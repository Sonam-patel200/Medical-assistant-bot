# Medical-assistant-bot
## Problem Statement
* We need to create a chatbot with Medical Question Answer Dataset
### Approach to the Problem:
* We will create an encoder/decoder model that will take the data that we provide and output our response using the techniques of machine translation.
**At a very high level, an encoder-decoder model can be thought of as two blocks, the encoder and the decoder connected by a vector which we will refer to as the ‘context vector’.**
* Encoder: The encoder processes each token in the input-sequence. It tries to cram all the information about the input-sequence into a vector of fixed length i.e. the ‘context vector’. After going through all the tokens, the encoder passes this vector onto the decoder.
* Context vector: The vector is built in such a way that it's expected to encapsulate the whole meaning of the input-sequence and help the decoder make accurate predictions. We will see later that this is the final internal states of our encoder block.
* Decoder: The decoder reads the context vector and tries to predict the target-sequence token by token.
## Assumptions made by our SEQ2SEQ Model:
1. Equal Importance of All Inputs: All tokens in the input sequence are treated equally, regardless of their position or relevance to the current decoding step. This means that the model does not explicitly prioritize certain parts of the input sequence over others during decoding.
2. Short-Term Dependencies: The model assumes that all relevant information needed to generate the output sequence is captured in the fixed-length representation obtained from the encoder. Therefore, it may struggle with capturing long-range dependencies or understanding context that spans across distant parts of the input sequence.
3. Context Compression: The fixed-length representation obtained from the encoder must compress all relevant information from the input sequence into a single vector. This means that important details from the input sequence may be lost or diluted in the encoding process.
## Model Performance:
* LOSS FUNCTION USED:-**SparseCategoricalCrossentropy** with masking layer to ignore the padding of 0 for maintaining uniform length.
## Metrics used to find validation accuracy:
* We compare the predicted sentence to the true sentene and try to find out the number of words correctly predicted as n_correct to the total nuumber of words in the sentence.
* Our accuracy come out to be =n_correct/n_total
Model performance is graphical shown in code file attached wrt number of epoch done.

