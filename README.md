from nltk.tokenize import word_tokenize, sent_tokenize
import nltk
nltk.download('punkt')

with open(r"/content/sample_data/HP book1.txt", encoding='utf-8') as f:

    text = f.read()
words  = word_tokenize(text.lower())
print(words)

alohomora_count = 0 
for i in words:
  if i =="Алохомора":
    alohomora_count +=1 
print(alohomora_count)

with open (r"/content/sample_data/spells_clean.txt", encoding='windows-1251') as file :
  spells = file.readlines()
print(spells)
spell_counts = {spell.strip(): words.count(spell.strip()) for spell in spells}
print(spell_counts)
print(sorted(spell_counts.items(), key=lambda x: x[1],reverse=True))
