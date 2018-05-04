
```
.aNewline {
    position: relative;
    line-height: 1.4em;
    max-height: 2.8em;
    overflow: hidden;
}
```

```
.aNewline::after {
    content: "...";
    font-weight: bold;
    position: absolute;
    bottom: 0;
    right: 0;
    padding: 0 20px 1px 0.7em;
    background: #fff;
}
```

```
{
    color: #000;
    width: 100%;
    height: 45px;
    text-overflow: -o-ellipsis-lastline;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
}

```
