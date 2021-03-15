---
title: Reguły inspekcji
description: Zasady inspekcji służą do oceniania raportów z wydatków, faktur od dostawcy i zamówień zakupu, aby się upewnić, że spełniają one utworzone przez Ciebie reguły zasad. Wszystkie reguły skojarzone z zasadą inspekcji są uruchamiane w trybie wsadowym, zgodnie z harmonogramem określonym przez użytkownika.  Każda reguła zasad jest wystąpieniem typu reguły zasad. Dla każdego typu reguły zasad w danej chwili może być aktywna tylko jedna reguła.
author: panolte
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998d4dbabec74528b4acb9e797faef0c449e7c28
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021248"
---
# <a name="audit-policy-rules"></a>Reguły inspekcji

[!include [banner](../includes/banner.md)]

Zasady inspekcji służą do oceniania raportów z wydatków, faktur od dostawcy i zamówień zakupu, aby się upewnić, że spełniają one utworzone przez Ciebie reguły zasad. Wszystkie reguły skojarzone z zasadą inspekcji są uruchamiane w trybie wsadowym, zgodnie z harmonogramem określonym przez użytkownika.  Każda reguła zasad jest wystąpieniem typu reguły zasad. Dla każdego typu reguły zasad w danej chwili może być aktywna tylko jedna reguła. 

<a name="queries-and-query-types"></a>Kwerendy i typy kwerend
-----------------------

Tworząc regułę zasad inspekcji, najpierw należy zaznaczyć typ reguły zasad. Typ reguły zasad określa drzewo obiektów aplikacji (Application Object Tree — AOT), które ma być używane jako punkt wyjścia dla tworzenia reguły zasad. Określa również typ kwerendy używany dla reguły zasad. Kwerenda określa dokument źródłowy, który ocenia reguła zasad. Określa również pola w dokumencie źródłowym, które identyfikują zarówno podmiot prawny, jak i datę stosowaną po wybraniu dokumentów w celu inspekcji. Typ kwerendy kontroluje domyślne pola na stronie kwerendy i na stronie Reguła inspekcji. Poniższa tabela zawiera typy kwerend, które są dostępne dla reguł zasad inspekcji.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ kwerendy</th>
<th>Cel</th>
<th>Więcej informacji</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Warunkowe</td>
<td>Oceń atrybuty dokumentu źródłowego pod kątem określonych wartości.</td>
<td></td>
</tr>
<tr class="even">
<td>Agregacja</td>
<td>Oceń wiele dokumentów źródłowych lub wierszy dokumentu źródłowego pod kątem reguły zasad poprzez zsumowanie wartości liczbowych.</td>
<td></td>
</tr>
<tr class="odd">
<td>Próbkowanie</td>
<td>Losowo wybierz określony procent dokumentów źródłowych w celu oceny pod kątem naruszenia zasad.</td>
<td>Po wybraniu tej opcji należy użyć strony Reguła inspekcji, aby określić procent dokumentów losowo wybranych do inspekcji.</td>
</tr>
<tr class="even">
<td>Duplikat</td>
<td>Oceń dokumenty źródłowe, aby określić, czy zawierają zduplikowane wpisy w określonych polach.</td>
<td>Po wybraniu tej opcji użyj strony Reguła inspekcji, aby określić liczbę dni dodawanych do początku zakresu dat wyboru dokumentów, jeśli dokumenty są oceniane pod kątem zduplikowanych wpisów.</td>
</tr>
<tr class="odd">
<td>Wyszukiwanie wg listy</td>
<td>Oceń dokumenty źródłowe pod kątem konkretnych obiektów.</td>
<td>Dokument główny kwerendy określa dokument podlegający inspekcji. Kwerenda musi być kwerendą listy, która zawiera odwołanie do tabeli dirpartytable. Ta opcja może być używana wyłącznie z następującymi kwerendami AOT:
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (Pracownicy etatowi monitorowani w raporcie z wydatków)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Dostawcy monitorowani w zamówieniu zakupu)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (Dostawcy monitorowani w fakturze od dostawcy)</li>
</ul>
Po wybraniu tej opcji określ monitorowane jednostki na stronie Reguła inspekcji.</td>
</tr>
<tr class="even">
<td>Wyszukiwanie wg słów kluczowych</td>
<td>Oceń dokumenty źródłowe, aby określić, czy zawierają określone wyrazy.</td>
<td>Po wybraniu tej opcji określ słowa do wyszukania jednostki na stronie Reguła inspekcji. Strona Reguła inspekcji zawiera również opcje, które pozwalają wybrać tabele i pola do oceny pod kątem wprowadzonych wyrazów.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Wspólne parametry
Wszystkie reguły zasad dotyczące udziału konkretnych zasad inspekcji współdzielą te same parametry przetwarzania wsadowego i ten sam zakres dat wyboru dokumentów. Te parametry są określane w zasadzie na stronie Opcje dodatkowe .



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Naruszenia zasad audytu i sprawy](audit-policy-violations-cases.md)
[Definiowanie zasad inspekcji dla dokumentów źródłowych](tasks/define-audit-policies-source-documents.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]