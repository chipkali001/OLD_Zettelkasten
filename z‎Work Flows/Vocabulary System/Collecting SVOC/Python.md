``` python
for n in range(50000): 

    word= input("Enter The Word You Want To Learn About :") 

    d1= '[https://www.macmillandictionary.com/spellcheck/american/?q=](https://www.macmillandictionary.com/spellcheck/american/?q=)' + word 

    d2= '[https://www.collinsdictionary.com/dictionary/english/](https://www.collinsdictionary.com/dictionary/english/)' + word 

    d3= '[https://idioms.thefreedictionary.com/](https://idioms.thefreedictionary.com/)' + word 

    d4='https://www.google.com/search?q=google+dictionary#dobs=' + word 

    d5='https://ludwig.guru/s/' + word 

    d0= '[https://context.reverso.net/translation/english-french/'+](https://context.reverso.net/translation/english-french/'+) word 

    import webbrowser 

    webbrowser.open(d0) 

    webbrowser.open(d5) 

    webbrowser.open(d1) 

    webbrowser.open(d2) 

    webbrowser.open(d3) 

    webbrowser.open(d4)