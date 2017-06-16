## Play Pictionary with Jibo.

### Built in HackUMass 2016. (http://devpost.com/software/pictionary-with-jibo)

[Jibo SDK & API Documentation](https://developers.jibo.com/sdk/docs/)

#### Inspiration
Jibo is cute, and has cameras. What better game to play than pictionary? This game is an exercise both in the interactive capabilities as well as it's cameras.

#### What it does
First, ask Jibo to take a guess your drawing. It will take a picture and send it off to be classified by our custom-trained tensor flow neural networks. The first step uses openCV to detect the playing area within the board and crop off the rest of the image, and make it black and white. The image then gets passed off the our tensorflow model to be classified. We build trained neural network using hundreds of images pulled automatically from Bing Image Search. We used the "line drawing" category to limit it to pictures that look more like something drawn a whiteboard. We then supplemented the training data with a few examples of our own hand-drawn pictures. This network gives us a likelyhood for each possible label, which is sent back to Jibo. Then Jibo will go through these items one by one, listening for a "yes" or "no" from the user. There is an adorable celebration and frustration animation that plays when it gets the answer right or wrong. This continues until it exhausts its entire vocabulary, at which point it insults your artwork in protest!
