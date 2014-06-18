thuappendixbib
====

本宏包旨在为清华大学学位论文模板[ThuThesis](https://github.com/xueruini/thuthesis)提供附录参考文献支持。

本宏包依赖于`chapterbib`宏包。

使用方法
----

1.  将`thuappendixbib.sty`置于`main.tex`所在目录。
2.  在`main.tex`中引入本宏包。

    ```latex
    \usepackage{thuappendixbib}
    ```

3.  按如下方式在`main.tex`中增加附录。正文参考文献添加方式不变。

    ```latex
    % 参考文献
    \bibliographystyle{thubib}
    \bibliography{ref/refs}
    
    % ...
    
    % 附录
    \begin{appendix}
    \include{data/appendix01}
    \end{appendix}
    ```

4.  在附录对应的`data/appendix01.tex`文件中添加引用及参考文献。

    ```latex
    \chapter{外文资料的调研阅读报告}
    
    Hello world\cite{hello}!
    
    \bibliographystyle{thubib}
    \bibliography{ref/refs}
    ```

5.  按以下步骤编译文档（以使用XeLaTeX为例）。

    ```bash
    xelatex main
    bibtex data/appendix01
    bibtex main
    xelatex main
    xelatex main
    ```

    建议使用`latexmk`等工具自动完成整个编译过程以保证交叉引用正确。

已知问题
----

 *  使用本宏包时，仅在附录中引用的文献会同时出现在正文和附录的参考文献列表中。解决该问题的方法是为正文和附录指定不同的`.bib`文件，并保证仅在附录中引用的BibTeX条目不出现在正文使用的`.bib`文件中。
