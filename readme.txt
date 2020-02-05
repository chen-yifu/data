***README***: below are the descriptions of the key names you will find after loading the json file into python

***INSTRUCTIONS***:
To load the json into python, try:

with open('charles_example.json', 'r') as fp:
  data = json.load(fp)

***KEY DESCRIPTIONS***:

sub_author = original poster's username

sub_author_flar = original poster's flair if it exists, or None if it doesn't

sub_body = the text of the original post

sub_time = the time of the original post in Unix time format

sub_score = the score of the post

sub_body_inference = the inference results from ABSA. The inference results are broken down by sentence, where pairs of aspects and opinions will be found for each sentence. Examples of extracting this are written below

comments = a string that can be converted to json by using json.loads(strhere) with the same key formatting as before except with comment instead of sub in the name (eg. comment_author, comment_body_inference, etc.) I would recommend for now not worrying about the comments and just focusing on the original posts


***EXAMPLES***

To get the username of the first post's author:

data[0]['sub_author']

To get the username of the second post's author:

data[1]['sub_author']

To get the inference results for first sentence of the first post:

data[0]['sub_body_inference']['_sentences'][0]

Inference results for the second sentence of the first post:

data[0]['sub_body_inference']['_sentences'][1]

To get the first inference pair of aspect/opinion results for the first sentence of the first post:

data[0]['sub_body_inference']['_sentences'][0]['_events'][0]
	
