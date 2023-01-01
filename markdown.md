# Markdown Cheatsheet
마크다운은 사실 매일 사용해서 다 알지만, 표만들 때 귀찮아서 복붙하려고 만듬

### References

- 테이블만들때 :  [Table Generator](https://www.tablesgenerator.com/markdown_tables)
- 테이블 변환해서 쓸때 : [Table Convert](https://tableconvert.com/markdown-generator)
- 써보고 싶은 에디터 : [IA](https://ia.net/writer)
- [devhints.io](https://devhints.io/)
- [markdownguide.org](https://www.markdownguide.org/)


### 헤더

``` markdown
# h1
## h2
### h3
#### h4
##### h5
###### h6
```

```markdown
Header 1
========
```

```markdown
Header 2
--------
```

### 표

```markdown
| Column 1 Heading | Column 2 Heading |
| ---------------- | ---------------- |
| Some content     | Other content    |
```

```markdown
Column 1 Heading | Column 2 Heading
--- | ---
Some content | Other content
```

### 텍스트 강조

```markdown
*italic*
_italic_
```

```markdown
**bold**
__bold__
```

```markdown
***bold italic***
___bold italic___
```

```markdown
~~strikethrough~~
```

```markdown
`code`
```

### 리스트

```markdown
* Item 1
* Item 2
```

```markdown
- Item 1
- Item 2
```

```markdown
- [ ] Checkbox off
- [x] Checkbox on
```

```markdown
1. Item 1
2. Item 2
```

### 링크 

```markdown
[link](http://google.com) // 얘만 깃헙에서 먹히는 듯?
```

```markdown
[link][google]
[google]: http://google.com
```

```markdown
<http://google.com>
```

### 이미지

```markdown
![Image alt text](/path/to/img.jpg)
![Image alt text](/path/to/img.jpg "title")
![Image alt text][img]
```

```markdown
[img]: http://foo.com/img.jpg
```

아이폰 스크린샷 보여주기에 최적화!
```markdown
<img width="250" src="http://foo.com/img.jpg"> 
```


### Code

```markdown
`inline code`
```

```
    4 space indent
    makes a code block
```

~~~markdown
```
code fences
```
~~~


~~~markdown
```js
codeFences.withLanguage()
```
~~~


### Blockquotes

``` markdown
> This is
> a blockquote
>
> > Nested
> > Blockquote
```

### 가로선

```markdown
----
```

```markdown
****
```

