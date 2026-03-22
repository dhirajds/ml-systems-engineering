# you might have heard about tokens.
# For simplicity, each word is a token.
# Inputs given to the llm -> can be processed only as tokens.
# all the further process on that input happens on the sequence of tokens correspongint to it.



# But are words == tokens.-> might not be efficient.
# eg: we have a word like "flabbergasted" -> assigning a token to such rare word.
# is misuse of limited available token on a very rare word.

# Thats were tokenization algorithm comes to picture.
# tokens should be such that, it enhances the llms capability to handle inputs.

# Steps:
## splitting text into individual word and subword.
## convert the tokens in to token IDS
## get the embedding corresponding to this token ID. -> token embedding.

