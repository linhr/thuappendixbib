thuappendixbib
====

本宏包旨在为清华大学学位论文模板[ThuThesis](https://github.com/xueruini/thuthesis)提供附录参考文献支持。

使用方法
----

1.  将`thuappendixbib.sty`置于`main.tex`所在目录。
2.  在`main.tex`中引入本宏包。
    ```
    \usepackage{thuappendixbib}
    ```
3.  按如下方式在`main.tex`中增加附录。正文参考文献添加方式不变。
    ```
    % 参考文献
    \bibliographystyle{thubib}
    \bibliography{ref/refs}
    
    % ...
    
    % 附录
    \begin{appendix}
    \include{data/appendix01}
    \end{appendix}
    ```
4.  在附录对应的`data/appendix01.tex`文件中添加参考文献。
    ```
    \chapter{外文资料的调研阅读报告}
    
    Hello world\cite{hello}!
    
    \bibliographystyle{thubib}
    \bibliography{ref/refs}
    ```
