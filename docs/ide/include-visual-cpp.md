---
title: '&lt;include&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- include
- <include>
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
ms.openlocfilehash: 0d03ee6e327eb95e63cec16f3886d616c909c3df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451975"
---
# <a name="ltincludegt-visual-c"></a>&lt;include&gt; (Visual C++)

\<include> タグを使用して、ソース コード内の型とメンバーを記述する別のファイル内のコメントを参照することができます。 これは文書化のコメントをソース コード ファイル内に直接配置する方法の代替です。  たとえば、\<include> を使用し、チームまたは会社全体で使用する標準の "定型" コメントを挿入できます。

## <a name="syntax"></a>構文

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
文書を含むファイルの名前。 ファイル名をパスで修飾することができます。  名前は、一重引用符または二重引用符で囲みます。  コンパイラは、`filename` が見つからない場合に警告を発行します。

*tagpath*<br/>
ファイルに含まれている目的のノードセットを選択する有効な XPath 式。

*name*<br/>
コメントの前に配置するタグの名前指定子。`name` には `id` が指定されます。

*ID*<br/>
コメントの前に配置するタグの ID。  名前は、一重引用符または二重引用符で囲みます。

## <a name="remarks"></a>コメント

\<include> タグは XML XPath 構文を使用します。 \<include> の使用をカスタマイズする方法については、XPath に関するドキュメントを参照してください。

コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

これは、複数ファイルの例です。 \<include> を使用する最初のファイルには、次のドキュメント コメントが含まれています。

```cpp
// xml_include_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_include_tag.dll

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />
public ref class Test {
   void TestMethod() {
   }
};

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />
public ref class Test2 {
   void Test() {
   }
};
```

2 番目のファイル xml_include_tag.doc には、次のドキュメントのコメントが含まれています。

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>プログラムの出力

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>t2</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>参照

[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)