#Trie树:字典树,使用数结构存储字符串

```c++
//son[][26]指向子节点
//0号既是根节点又是空节点
//cnt[]储存以每个节点结尾的单词的数量

int son[N][26],cnt[N],idx;

void insert(char *str)
{
    int p = 0;
    for(int i = 0;str[i];i ++)
    {
        int u = str[i] - 'a';
        if(!son[p][u]) son[p][u] = ++idx;
        p = son[p][u];
    }
    cnt[p] ++;
}

//查询字符串出现次数
void query(char *str)
{
    int p = 0;
    for(int i = 0;str[i];i ++)
    {
        int u = str[i] - 'a';
        if(!son[p][u]) return 0;
        p = son[p][u];
    }
    return cnt[p];
}
```




