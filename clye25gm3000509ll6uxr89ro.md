---
title: "211. Design Add and Search Words Data Structure"
datePublished: Tue Jul 09 2024 06:56:25 GMT+0000 (Coordinated Universal Time)
cuid: clye25gm3000509ll6uxr89ro
slug: 211-design-add-and-search-words-data-structure
tags: dsa

---

Design a data structure that supports adding new words and finding if a string matches any previously added string.

Implement the `WordDictionary` class:

* `WordDictionary()` Initializes the object.
    
* `void addWord(word)` Adds `word` to the data structure, it can be matched later.
    
* `bool search(word)` Returns `true` if there is any string in the data structure that matches `word` or `false` otherwise. `word` may contain dots `'.'` where dots can be matched with any letter.
    

**Example:**

```python
Input
["WordDictionary","addWord","addWord","addWord","search","search","search","search"]
[[],["bad"],["dad"],["mad"],["pad"],["bad"],[".ad"],["b.."]]
Output
[null,null,null,null,false,true,true,true]

Explanation
WordDictionary wordDictionary = new WordDictionary();
wordDictionary.addWord("bad");
wordDictionary.addWord("dad");
wordDictionary.addWord("mad");
wordDictionary.search("pad"); // return False
wordDictionary.search("bad"); // return True
wordDictionary.search(".ad"); // return True
wordDictionary.search("b.."); // return True
```

**Constraints:**

* `1 <= word.length <= 25`
    
* `word` in `addWord` consists of lowercase English letters.
    
* `word` in `search` consist of `'.'` or lowercase English letters.
    
* There will be at most `2` dots in `word` for `search` queries.
    
* At most `10<sup>4</sup>` calls will be made to `addWord` and `search`.
    

Solution:

```python
class TrieNode:
    def __init__(self):
        self.children = {}  # a : TrieNode
        self.word = False


class WordDictionary:
    def __init__(self):
        self.root = TrieNode()

    def addWord(self, word: str) -> None:
        cur = self.root
        for c in word:
            if c not in cur.children:
                cur.children[c] = TrieNode()
            cur = cur.children[c]
        cur.word = True

    def search(self, word: str) -> bool:
        def dfs(j, root):
            cur = root

            for i in range(j, len(word)):
                c = word[i]
                if c == ".":
                    for child in cur.children.values():
                        if dfs(i + 1, child):
                            return True
                    return False
                else:
                    if c not in cur.children:
                        return False
                    cur = cur.children[c]
            return cur.word

        return dfs(0, self.root)
```