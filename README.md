
# PDF READER

import pyttsx3
import PyPDF2

book=open("at_your_age.pdf","rb") # enter a pdf name
pdfreader=PyPDF2.PdfFileReader(book)
pages=pdfreader.numPages
print(pages)

speaker=pyttsx3.init()
page=pdfreader.getPage(1) # to read from particular page
text=page.extractText()
speaker.say(text)
speaker.runAndWait()
