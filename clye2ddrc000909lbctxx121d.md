---
title: "208. Implement Trie (Prefix Tree)"
datePublished: Tue Jul 09 2024 07:02:35 GMT+0000 (Coordinated Universal Time)
cuid: clye2ddrc000909lbctxx121d
slug: 208-implement-trie-prefix-tree-1
tags: dsa

---

A [**trie**](https://en.wikipedia.org/wiki/Trie) [(pro](https://en.wikipedia.org/wiki/Trie)nounced as "try") or **prefix tree** is a tree data structure used to efficiently store and retrieve keys in a dataset of strings. There are various applications of this data structure, such as autocomplete and spellchecker.

Impleme[nt t](https://en.wikipedia.org/wiki/Trie)he Trie class:

* `Trie()` [Init](https://en.wikipedia.org/wiki/Trie)ializes the trie object.
    
* `void in`[`sert`](https://en.wikipedia.org/wiki/Trie)`(String word)` Inserts the string `word` into the trie.
    
* `boolean` [`sea`](https://en.wikipedia.org/wiki/Trie)`rch(String word)` Returns `true` if the string `word` is in the trie (i.e., was inserted before), and `false` otherwise.
    
* `boolean` [`sta`](https://en.wikipedia.org/wiki/Trie)`rtsWith(String prefix)` Returns `true` if there is a previously inserted string `word` that has the prefix `prefix`, and `false` otherwise.
    

**Exam**[**ple 1:**](https://en.wikipedia.org/wiki/Trie)

```python
Input
["Trie", "insert", "search", "search", "startsWith", "insert", "search"]
[[], ["apple"], ["apple"], ["app"], ["app"], ["app"], ["app"]]
Output
[null, null, true, false, true, null, true]

Explanation
Trie trie = new Trie();
trie.insert("apple");
trie.search("apple");   // return True
trie.search("app");     // return False
trie.startsWith("app"); // return True
trie.insert("app");
trie.search("app");     // return True
```

**Cons**[**traints**](https://en.wikipedia.org/wiki/Trie)**:**

* `1 <= wo`[`rd.l`](https://en.wikipedia.org/wiki/Trie)`ength, prefix.length <= 2000`
    
* `word` an[d `pr`](https://en.wikipedia.org/wiki/Trie)`efix` consist only of lowercase English letters.
    
* At most [`3 *`](https://en.wikipedia.org/wiki/Trie) `10<sup>4</sup>` calls **in total** will be made to `insert`, `search`, and `startsWith`.
    

Solution:

```python
class PrefixTreeNode:
    def __init__(self):
        """
        index reprenset which char
        """
        self.children = {}
        self.end = False

class PrefixTree:
    def __init__(self):
        self.root = PrefixTreeNode()

    def insert(self, word: str) -> None:
        curr = self.root
        for c in word:
            if c not in curr.children:
                curr.children[c] = PrefixTreeNode()
            curr = curr.children[c]
        curr.end = True

    def search(self, word: str) -> bool:
        curr = self.root
        for c in word:
            if c not in curr.children:
                return False
            curr = curr.children[c]
        return curr.end

    def startsWith(self, prefix: str) -> bool:
        curr = self.root
        for c in prefix:
            if c not in curr.children:
                return False
            curr = curr.children[c]
        return True
```