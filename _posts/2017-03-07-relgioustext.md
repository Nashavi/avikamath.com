---
header: 
  overlay_image: /assets/images/religions.jpg
  teaser: /assets/images/religions.jpg
  overlay_filter: 0.3 
  caption: "Photo Credits: [friendshipchristianchurch](http://friendshipchristianchurch.org/wp-content/uploads/2014/03/Relgions-a-comparison.gif)"
title: Mining for Sentiments and Ideas in Religious Books
excerpt: "The Bhagavad Gita, The King James Bible, The Quran and The Tao Te Ching. How do they compare to each other?"
comments: true
updated: 2017-03-07
---

**The Bhagavad Gita, The King James Bible, The Quran and The Tao Te Ching!** These 4 religious texts come from 7 major religions of the world and over [70% of the world population](https://en.wikipedia.org/wiki/List_of_religious_populations) believe them to be a guide to live life by. These religions have evolved over time, defined cultures and to a certain extent even defined political boundaries. Have these religions really been so well-defined and different from each other? Don't they all have the same philosophies? Don't they all emphasize on similar ideas? I wanted to make a comparative analysis of these 4 texts, understand the ideas they emphasize on, extract sentiments and associations. Enter text analytics!

{% include toc title="Text Mining Religious Books" icon="file-text" %}

Text analytics is the process of analyzing unstructured raw data, extracting relevant information from it and transforming it into useful business information. Text Analytics has a wide range of application from ranging sentiment analysis, creating spam filters , automatic ad placements, social media monitoring to extracting competitive intelligence, national security, competitive intelligence and scientific discovery.

{% capture notice-2 %}
A recently released package [tidytext](http://tidytextmining.com/) by [Julia Silge](https://twitter.com/juliasilge) and [David Robinson](https://twitter.com/drob) for R has some awesome incredible capabilities to do some heavy lifting with text. This mini-project was also a way to get used to this package while understanding some philosophical ideas from these sacred texts.
{% endcapture %}

<div style="font-size:12px">
  {{ notice-2 | markdownify }}
</div>

Since these sacred books are not originally in English I relied on translations by Shri Purohit Swami for [The Bhagavad Gita](http://www.ulc.org/wp-content/uploads/2012/10/Bhagavad-Gita.pdf), Abdullah Yusuf Ali for [The Holy Quran](http://streathammosque.org/uploads/quran/english-quran-yusuf-ali.pdf), The Project Gutenberg Edition for [The King James Bible](http://www.gutenberg.org/cache/epub/10/pg10.txt), James Legge for [The Tao Te Ching](http://www.gutenberg.org/cache/epub/216/pg216.txt). **_The analysis is completely done as a research and I have tried to provide an unbiased representation of the results of data mining._**

### Flow of Sentiments
<figure style="width: 1200px">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/Flow of Sentiments.jpeg" alt="">
</figure> 

The above chart shows the changes in net sentiments as we proceed through each sections of the sacred texts. Each bar is indicative of a particular section in the text if the entire text was scaled to be at 100.

- The Bhagavad Gita starts off with negative sentiments. These refer to _Chapter one: The Despondency of Arjuna_ and initial sections of _Chapter Two: The Philosophy of Discrimination_ where Arjuna gets dejected as he fears losing friends and relatives as a consequence of the Mahabharata war. In the initial sections of Chapter Two, Lord Krishna consoles Arjuna.
- The KJV sections 62% - 67% comprise of highly negative sentiments. These sections refer to:
  * _Jeremiah_, the most persecuted prophet of the Bible, with features stressing on repentance and prophecy [<sup>1</sup>](https://www.christiancourier.com/articles/747-marvelous-book-of-jeremiah-the)
  * _Lamentations_, poetic laments for the destruction of Jerusalem [<sup>2</sup>](https://en.wikipedia.org/wiki/Book_of_Lamentations)
- In The Holy Quran has sections 70%- 75% that are highly negative. These sections refer to _Surah: Al Maidah_ verse: 27 to verse: 92 that has three main topics: Commandments and instructions about life of Muslims, admonition to the Muslims and admonition to the Jews and the Christians. [<sup>3</sup>](http://englishtafsir.com/Quran/5/index.html)

### Negative vs Positive sentiments

![totalsentiments](/assets/images/Total sentiments.jpeg)

The Bhagavad Gita comprises a net positive sentiment where The King James Bible and The Quran have more of negative sentiments in them. The Tao Te Ching seems to have a perfect balance between positive and negative sentiments.

### Top Sentiments in each text

![Topsentiments](/assets/images/Top 20 sentiments.jpeg)

Clearly, from the above plot, there are common ideas across these religions. Let's look at the common negative and positive words separately to get a better idea out of them. The plot below indicates sentiments that are common among all text.

![Common Sentiments Radar2](/assets/images/Common Sentiments Radar2.jpg)

### Differentiators of each text (TF-IDF)

Moving away from sentiments, lets see what words are unique to each text. For this purpose, we would use [TF-IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) which is a statistical measure to determine the importance of a word to a specific document compared to its existence in other documents.

![Topuniquewords](/assets/images/Top Unqiue words.jpeg)

As expected these unique word are mostly nouns. However it also helps to shed some light on some major ideas that are unique to each religion. ‘Renunciation’, ‘Self-knowledge’, ‘intellect’ are some of the recurring ideas in Hinduism. It also points out the archaic usage of the word ‘spake’ in The King James Bible. The Quran has its most of its unique ideas around Allah being the protector, oft-forgiving correctly identified. It would be easier to catch on the unique ideas from The Tao Te Ching since it does not have any character names/ proper nouns.

### Associations among words

A graphical visualization of bi-gram (sequence of two adjacent words) should also give some unique ideas in each of these texts.

![Bi-gram Graph](/assets/images/Bigram Graph2.jpeg)

Only top 50 bigrams are used to create the above plot. It is possible to create more complex relationships where all the words in the text are chained with each other. The darkness of the arrows indicate stronger relationships between the words. 

The Bhagavad Gita forms a cluster of words around ‘thy’, ‘thou’ indicating its guidance to the reader/Arjuna. The tri-gram ‘Lord Shri Krishna’ have the strongest relationship and it is followed by ‘replied/continued’ indicating on-going dialogues. Similar to The Gita, The King James Bible also has a set of 2 clusters around ‘thy’ and ‘thou’. The Quran has a strong cluster of words around ‘Allah’. As with the other two texts, there are clusters around ‘thou’  and ‘ye’. Clearly, The Tao Te Ching is far too short text that it has just 3 recurring bi-grams in it. 

### Conclusion

Any text analytics project requires extensive cleaning. In this case, the input data was fairly cleaner than a real life text data say from an email/ im/ text messages. Still, I could have added to the accuracy of the measures I used by [stemming](https://en.wikipedia.org/wiki/Stemming) algorithms on the words before analyzing them and even standardizing the words by replacing them with common synonyms. I could even go a step ahead by using a part of speech tagging in order to identify the nouns, adjective, verbs in sentences that is available through OpenNLP or qdap packages. 

All the work above was done in R and the entire code is available in [my github](https://github.com/Nashavi/ReligionStudy)
