---
header: 
  overlay_image: /assets/images/religions.png
  overlay_filter: 0.3 
  caption: "Photo Credits: http://friendshipchristianchurch.org"
title: Mining for Sentiments and Ideas in Religious Books
updated: 2017-03-07
---

Text analytics is the process of analyzing unstructured raw data, extracting relevant information from it and transforming it into useful business information.   Text Analytics has a wide range of application from ranging sentiment analysis, creating spam filters , automatic ad placements, social media monitoring to extracting competitive intelligence, national security, competitive intelligence and scientific discovery.

Talking in terms of R, a recently released package [tidytext](http://tidytextmining.com/) by [Julia Silge](https://twitter.com/juliasilge) and [David Robinson](https://twitter.com/drob) has some awesome incredible capabilities to do some heavy lifting with text. So I decided to try it out myself and learn some things by doing some text mining on religious texts. The idea was to get used to the package as well as get to understand some philosophical ideas from these sacred texts.

The Bhagavad Gita, The King James Bible, The Quran and The Tao Te Ching! These 4 religious texts come from 4 of the 7 major religions of the world and over [70% of the world population](https://en.wikipedia.org/wiki/List_of_religious_populations) believe them to be a guide to live life by. I wanted to make a comparative analysis of these 4 texts, understand the ideas they stress on, extract sentiments and associations.

Since these sacred books are not originally in English I relied on translation by Shri Purohit Swami for [The Bhagavad Gita](http://www.ulc.org/wp-content/uploads/2012/10/Bhagavad-Gita.pdf), Abdullah Yusuf Ali for [The Holy Quran](http://streathammosque.org/uploads/quran/english-quran-yusuf-ali.pdf), The Project Gutenberg Edition for [The King James Bible](http://www.gutenberg.org/cache/epub/10/pg10.txt), James Legge for [The Tao Te Ching](http://www.gutenberg.org/cache/epub/216/pg216.txt). _The analysis is completely done as a research and I have tried to provide an unbiased representation of the results of data mining._

### Flow of Sentiments

![sentimentflow](/assets/images/Flow of Sentiments.jpeg)


The above chart shows the changes in net sentiments as we proceed through each sections of the sacred texts. Each bar is indicative of a particular section in the text if the entire text was scaled to be at 100.

- The Bhagavad Gita starts off with negative sentiments. These refer to Chapter one: The Despondency of Arjuna and initial sections of Chapter Two: The Philosophy of Discrimination where Arjuna gets dejected as he fears losing friends and relatives as a consequence of the Mahabharata war. Initial sections of Chapter Two section is where Lord Krishna consoles him.
- The KJV sections 62% - 67% is a section comprising of highly negative sentiments. These sections comprise of :
-- Jeremiah, the most persecuted prophet of the Bible, with features stressing on repentance and prophecy [source](https://www.christiancourier.com/articles/747-marvelous-book-of-jeremiah-the)
-- Lamentations, poetic laments for the destruction of Jerusalem
- In The Holy Quran the section 70%- 75% are also highly negative. This section refers to Surah: Al Maidah verse: 27 to verse: 92 which comprises three main topics: Commandments and instructions about life of Muslims, admonition to the Muslims and admonition to the Jews and the Christians.
