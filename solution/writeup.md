
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

After trying multiple recipes in cyberchef, we get one particular output from using <mark>from Base64<mark>.

<img width="1182" height="754" alt="image" src="https://github.com/user-attachments/assets/ba15a23f-9bcf-4c09-8572-1008c5b63e08" />

`2.334836814727976`

Looks like a part of GPS coordinates, let us try to find the other part of it.

I tried using binwalk to see if there any zip files embedded into the file.

<img width="734" height="185" alt="image" src="https://github.com/user-attachments/assets/a56ed1bd-2087-4b6b-a040-34223c8ac11f" />

Seems like there is one, we shall attempt to find out what is inside it.

Using binwalk again to extract the files embedded inside, we see that there is a text file available.

<img width="765" height="384" alt="image" src="https://github.com/user-attachments/assets/a8490694-243a-48ce-9199-4a103ef64b32" />

`frnfbagjb.txt`

File name could be something that is encrypted, let's put it onto cyberchef.

Again, trying multiple recipes in cyberchef, we get output <mark>from ROT13<mark>.

<img width="1175" height="679" alt="image" src="https://github.com/user-attachments/assets/5de261e0-6c41-4d5c-a2d7-de77dca050f2" />

`seasontwo`

Huh? Could this be referring to some sort of series? Since the second part of the flag is said to be "date released" so it could be so.

Now let us check the content inside this text file.

<img width="499" height="48" alt="image" src="https://github.com/user-attachments/assets/b23cec62-cb99-4c17-a799-196610477eef" />

`NDguODg4OTk1MzIyNzA0NTM=`

This could be the second part of the GPS coordinates since it ends with an equal sign, why don't we put decode it again.

<img width="1174" height="642" alt="image" src="https://github.com/user-attachments/assets/3138ca00-55f4-40e0-9df7-519acdd4f56f" />

Aha! There we get the second part of the GPS coordinates.

`48.88899532270453`

This leads us to the point:

<img width="807" height="611" alt="image" src="https://github.com/user-attachments/assets/5d411d2c-a257-4baf-ab30-ba4577b4b7a7" />

There is a bakery near this coordinate.

<img width="1398" height="787" alt="image" src="https://github.com/user-attachments/assets/d8f83ac1-32fb-4d10-a3bd-436408a44076" />

`Boris - Boulangerie`

It is the bakery in Paris, the one the writer was talking about.

We shall now check the reviews as the writer liked putting reviews online.

Using the filters baguette and recently posted, and after scrolling a bit, we get this particular review by someone named Henry Lin.

<img width="784" height="682" alt="image" src="https://github.com/user-attachments/assets/c5b183f9-0574-4326-8ed5-bc82d1d0c410" />

This person visited in January and also bought baguettes along with bread with olives, so its clear that it is this one. The review also talks more about the strange day that we saw in the letter.

There is it also seen that the writer's job which is also the missing person's job is **Local Guide**. Thus we get the first part of the flag.

Apparently they have seen some sort of giant snowman and two figures following behind? ..What?

Anyways, now let us search more about this bakery to find some sort of clue.

After scanning some articles and posts about this bakery, I uncovered that this bakery is very famous for being in a French animated superhero television series called **Miraculous: Tales of Ladybug & Cat Noir**

<img width="741" height="149" alt="image" src="https://github.com/user-attachments/assets/1f6bd955-aa00-412e-a437-8e302a60872b" />

(From: https://www.reddit.com/r/miraculousladybug/comments/rxm9uc/today_i_visited_the_boris_lum%C3%A9_boulangerie_the/)

<img width="663" height="299" alt="image" src="https://github.com/user-attachments/assets/e5cc27df-e1e4-4da3-b598-ef9772144603" />

(From: https://mindtrip.ai/attraction/paris-ile-de-france/boris-boulangerie/at-8nd1RNIc)

This explains the strange review that Henry left about seeing a "bug lady fixing everything with a miraculous power". 

So is Henry inside the series? Explains why he's missing.

In order to find the second part of the flag which is the release date, let's focus on the part where he says he saw some giant snowman. This could be included in season two as we found out earlier.

<img width="775" height="466" alt="image" src="https://github.com/user-attachments/assets/947396f2-fb46-4ef9-b3bc-c196b1579bd4" />

<img width="566" height="208" alt="image" src="https://github.com/user-attachments/assets/125781c8-0e51-4380-b176-c1da56f714fd" />

(From: https://miraculousladybug.fandom.com/wiki/Andr%C3%A9)

This could be the snowman that Henry saw, which is also called Glaciator. This is featured in the Glaciator episode of the series. Now finding the release date:

<img width="323" height="292" alt="image" src="https://github.com/user-attachments/assets/79c4cdfe-3336-4cc9-ac6e-e241a2dd3867" />

(From: https://miraculousladybug.fandom.com/wiki/Glaciator)

Since it was in January, the release date is January 14th, 2018.

This gives us the complete flag : `flag{localguide_140118}`


