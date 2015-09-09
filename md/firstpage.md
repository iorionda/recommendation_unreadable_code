## Unreadable code のススメ
<b><!-- --></b>  
<b><!-- --></b>  
Created by [Iori ONDA](https://github.com/iorionda)  
http://twitter.com/120reset

---

### おまえら読みやすいコード書いてるか？

---

# 捨てろ

---

![甘い考えを捨てろ](http://wikiwiki.jp/viplcb/?plugin=ref&page=%B4%C5%A4%A8%A4%F2%BC%CE%A4%C6%A4%ED&src=amae.JPG)

---

## 読みにくいコードの世界

* Esolang
* Obfuscated Code
* Quine
* ...

---

![なんだってー](http://www.mag2.com/collabo/mmr/img/na_nandatte.png)

---

# Esolang

---
難解プログラミング言語 (なんかいプログラミングげんご)とは、意図的に読解が困難なように設計されたプログラミング言語である。  
英語では、Esoteric programming language （略してesolangとも）と言われる。  

基本的には、実用性を目指したものではなく、冗談プログラミング言語  

---
## 代表的な Esolang をいくつか紹介

---

## みんな知ってる
# Brainfuck

---

Hello world

```
+++++++++[>++++++++>+++++++++++>+++++<<<-]>.>++.+++++++..+++.>-.
------------.<++++++++.--------.+++.------.--------.>+.
```

---

## おなじみ
# Whitespace

---

Hello world

```
   	  	   
	
     		  	 	
	
     		 		  
 
 	
  	
     		 				
	
     	     
	
     			 			
	
     		 				
	
     			  	 
	
     		 		  
	
     		  	  
	
     	    	
	
  
```

---

## 昨日知った
# قلب(Qalb)

---

hello world

```
(قول "مرحبا يا عالم!")
```

---

## タミル語 
# எழில்(Ezhill)

---
hello world

```
# தமிழில் ஒரு எடுத்துக்காடு

பதிப்பி "வணக்கம்!"
பதிப்பி "உலகே வணக்கம்"
பதிப்பி "******* நன்றி!. *******"
exit()
```

---

# じゃあこれは?

---

```
#include <stdio.h>
#include <stdlib.h>
  
int loop() {
    puts("Hello, world!");
    exit(0);
}
```

---

# そうだね、Ruby だね

---

# それはそうと

---

## 今日はQuineの話

---

# Quineとは?

---

クワイン（英: Quine）は、コンピュータプログラムの一種で、自身のソースコードと完全に同じ文字列を出力するプログラムである。 
<br></br>
Ken Thompson チューリング賞受賞の公演では  
「Quine を書いたことが無いのなら、自分で書いてみることを強くお勧めする」とのこと。

---

Q. 何が面白いの?

---

A. 考えるな、感じろ

![lee](http://userdisk.webry.biglobe.ne.jp/022/089/64/N000/000/005/136942775859313215391.jpg)

---

# 具体例

---

# Ruby

```ruby
eval s=%q($><<"eval s=%q(#{s})\n")
```

---

# 動かしてみる

---

# RubyでQuineを書いてみる 

---

# eval

---

### RubyにはQuineを書く為に用意された`eval`というメソッドがあります

基本的なアイデアは `eval` する文字列を変数に代入しておいて`eval`の中でその文字列を表示する

---

# 例えば

```
eval(q='puts q')
```
と書くと

```
puts q
```
が得られる  
なので、`puts q` の左側(`eval(q=`)と右側(`)`を  
出力してやればいいことがわかる

---

# %p記法

---

### RubyにはQuineを書く為に用意された`%p`という記法があります

`%p`を文字列に対して使うと、"で括られた文字列を生成してくれる

---

# つまり

---

```
eval(q="puts 'eval(q=%p)'%q") 
```

を実行すると

```
eval(q="puts 'eval(q=%p)'%q")
```

を得ることが出来る

---

# %w 記法

---

RubyにはQuineを書く為に用意された`%w`という記法があります

---

これと Array と Join を使えば、好きな位置に空白を入れることができる

---

```
eval %w"p
ut s 


'He
   ll
     o
             Wo
r
ld'
".join

#=> HelloWorld
```

---

AAを書くのに便利😤

---

## 基本はそんなとこ

---

当然、Ruby以外の言語でも出来る。  
自分は最初の Quine は C言語で書いた。

---

まとめ

---

A. 考えるな、感じろ

![lee](http://userdisk.webry.biglobe.ne.jp/022/089/64/N000/000/005/136942775859313215391.jpg)

---
