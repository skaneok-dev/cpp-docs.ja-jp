---
title: ptr::operator bool
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr::operator bool
- ptr.operator bool
- operator bool
- msclr::com::ptr::operator bool
- msclr.com.ptr.operator bool
helpviewer_keywords:
- ptr::operator bool
ms.assetid: 31123377-6ecd-4cef-9b75-3db3996fbcd1
ms.openlocfilehash: 185db15a62cc676c771f60a54c583e19e28e95be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509670"
---
# <a name="ptroperator-bool"></a>ptr::operator bool

使用するための演算子`com::ptr`条件式。

## <a name="syntax"></a>構文

```
operator bool();
```

## <a name="return-value"></a>戻り値

**true**所有されている COM オブジェクトが無効である場合**false**それ以外の場合。

## <a name="remarks"></a>Remarks

所有されている COM オブジェクトがない場合は、有効では`nullptr`します。

実際にこの演算子の変換`_detail_class::_safe_bool`よりも安全である`bool`整数型に変換できないためです。

## <a name="example"></a>例

この例の実装を使用する CLR クラス、`com::ptr`のプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。 `CreateInstance`メンバー関数を使用して`operator bool`が有効では、コンソールに出力する場合はかどうかを判断する新しい document オブジェクトを作成した後。

```
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>関連項目

[ptr のメンバー](../dotnet/ptr-members.md)<br/>
[ptr::operator!](../dotnet/ptr-operator-logical-not.md)