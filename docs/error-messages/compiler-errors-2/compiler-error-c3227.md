---
title: コンパイラ エラー C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: b175b14af55a9a462e040f064cc6e38d13fffb94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632493"
---
# <a name="compiler-error-c3227"></a>コンパイラ エラー C3227

'parameter': 'keyword' を使用して、ジェネリック型を割り当てることはできません

型をインスタンス化するために適切なコンス トラクターが必要です。 ただし、コンパイラでは、適切なコンス トラクターが使用できることを確認することはありません。

ジェネリックではなくテンプレートを使用するには、このエラーを解決するのには、またはいくつかのメソッドのいずれかを使用して、型のインスタンスを作成することができます。

## <a name="example"></a>例

次の例では、C3227 が生成されます。

```
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```