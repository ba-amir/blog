## Introduction
You've probably heard of AI text detectors such as gptzero and so on. You've 
also probably heard that their accuracy tends to be very low. If you've 
ever been interested in finding out how exactly these detectors tick and 
how accurate they can really be then you're in luck. *Communications of the ACM* 
published an article late last year surveying the common methods used in detecting 
llm-generated text. I found the article extremely fascinating and desperately needed 
to share it someone, by someone I meant the hopeless nerds reading this right now. 
This is just going to be an abridged version highlighting the sections I found really 
colourful supplemented with some additional reading. I highly recommend you read 
the original article.



## Black Box Methods 

Black box methods focus on analyzing output and classifying them based on 
criteria. 

## White Box Methods 

white box methods mostly revolve around creating some sort of watermark to 
identify llm-generated text. Creating this watermark is pretty tricky as it 
needs to be resistant to paraphrasing while being difficult to detect without 
prior knowledge and trivial to verify. 


Just implanting certain words into the llm output isn't good enough as that's pretty
easy to change just by using synonym words.

Inference-time watermarking is really cool. It basically divides words that 
could be output by the LLM into good and bad lists. The model then only 
uses words from the 'allowed' list. In order to check the watermark, the 
detector checks the frequency of the words in the 'banned' list. This didn't seem 
particular helpful at first but when you think about it, you see that it's not 
very likely that a piece of work would seem to avoid certain phrases. You also have
to be very careful with how many words are in the banned list as it could negatively 
impact the qualify of the output. 

Another method, that I found rather interesting was using the text's syntactic structure. 
