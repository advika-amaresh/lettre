
# lettre : Solution

We are given an image of a letter that was sent by the missing person.

<img width="1706" height="3709" alt="image" src="https://github.com/user-attachments/assets/6a788ba6-69ef-42df-baf6-08f1a7ed17b6" />

Looks like a letter that is written in French. Let us break it down piece by piece.

## Step 1 - Translate the image

When we run this image for translation using a translation app, we get;

<img width="959" height="2084" alt="image" src="https://github.com/user-attachments/assets/6f75aaf8-cfb5-414a-b23f-6f2910904ea6" />

Seems to be written by a person with the name "Lin" perhaps and addressed to a person called Anetta. The letter primarily talks about the writer's day which included going to the bakery.
One thing we can notice is, the writer mentions it was Epiphany recently, and a King Cake was additionally sent. 

Searching about this, I came across this one article that explains what it is.
<img width="833" height="175" alt="image" src="https://github.com/user-attachments/assets/cdf0f546-2852-448e-abfd-bc008e6e40bf" />

(Article from https://www.cia-france.com/blog/tips-for-learning-french/epiphany-french-tradition-culture)

From this, we can conclude that the letter was sent around January.

Another thing the writer mentions is about reviews. Maybe they love putting reviews online?
But we still do not know which bakery it is that the writer put a review about.

## Step 2 - Checking metadata

Time to dig deeper into this image. Let us use exiftool for this.
<img width="554" height="64" alt="image" src="https://github.com/user-attachments/assets/df722543-4bc4-4b86-b040-16e24435a118" />

Oh! We can see there is a comment that is attached to this picture.
<img width="562" height="117" alt="image" src="https://github.com/user-attachments/assets/11494573-d2b6-4fca-9164-cb09c5dbe703" />

`Mi4zMzQ4MzY4MTQ3Mjc5NzY=`

This is encrypted, let us try to decrypt it.

After trying multiple recipes, we get one particular output.

<img width="1182" height="754" alt="image" src="https://github.com/user-attachments/assets/ba15a23f-9bcf-4c09-8572-1008c5b63e08" />







**Flag format:** `flag{...}`

