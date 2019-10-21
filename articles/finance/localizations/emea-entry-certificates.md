---
title: Świadectwa wywozowe UE
description: Ten artykuł zawiera informacje dotyczące świadectw wywozowych umożliwiających wprowadzanie towarów na teren Unii Europejskiej (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46a4180163adea72e7d8712ed5ce6a3306e477c5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176160"
---
# <a name="eu-entry-certificates"></a>Świadectwa wywozowe UE

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące świadectw wywozowych umożliwiających wprowadzanie towarów na teren Unii Europejskiej (UE).

Można wykonać następujące zadania dla świadectwa wywozowego Unii Europejskiej (UE):

-   Tworzenie i wystawianie świadectwa wywozowego UE wraz z dokumentem faktury odbiorcy lub dokumentem dostawy towarów lub świadczenia usług do krajów/regionów UE.
-   Odbieranie świadectwa wywozowego UE podpisanego przez odbiorcę z UE.
-   Przesyłanie podpisanego świadectwa wywozowego UE otrzymanego od odbiorcy lub od osób trzecich, które są odpowiedzialne za dostarczanie towarów do odbiorcy.
-   Kojarzenie przesłanego świadectwa wywozowego UE z fakturą dla odbiorcy.
-   Aktualizowanie stanu przesłanego świadectwa wywozowego UE.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategoria</th>
<th>Wymaganie wstępne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Kraj/region</td>
<td>Podstawowy adres firmy musi być w Unii Europejskiej.</td>
</tr>
<tr class="even">
<td>Powiązane zadania konfiguracji</td>
<td><ul>
<li>Na stronie <strong>Parametry modułu rozrachunków z odbiorcami</strong> wybierz opcje <strong>Włącz zarządzanie świadectwami wywozowymi</strong> i <strong>Włącz opcję wystawiania świadectwa wywozowego</strong>.</li>
<li>Na stronie <strong>Odbiorcy</strong> na skróconej karcie <strong>Faktura i dostawa</strong> wybierz opcję <strong>Wymagane jest świadectwo wywozowe</strong>, aby wskazać, że świadectwo wywozowe UE jest wymagane dla odbiorcy. Zaznacz opcję <strong>Wystaw świadectwo wywozowe</strong>, aby wystawić świadectwo wywozowe UE firmy dla odbiorcy.</li>
<li>Na stronie <strong>Parametry modułu rozrachunków z odbiorcami</strong> wybierz kod sekwencji identyfikatorów dla odwołania <strong>Świadectwo wywozowe</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Powiązane transakcje</td>
<td><ul>
<li>Tworzenie konta odbiorcy.</li>
<li>Utwórz zamówienie sprzedaży.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a>Tworzenie, rejestrowania i przekazywanie świadectwa wywozowego UE
Świadectwo wywozowe UE można utworzyć automatycznie lub ręcznie. Świadectwo wywozowe UE jest tworzone i drukowane automatycznie podczas księgowania dokumentu dostawy lub faktury dla odbiorcy przy użyciu strony **Księgowanie dokumentu dostawy** lub **Księgowanie faktury**. Aby ręcznie utworzyć lub ponownie wydrukować świadectwo wywozowe UE dla faktury dla odbiorcy, należy użyć strony **Arkusz faktur**. Można też użyć strony **Arkusz świadectwa wywozowego**, aby podać szczegóły dotyczące świadectwa wywozowego UE wystawionego przez inną firmę.

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a>Tworzenie świadectwa wywozowego UE automatycznie lub ręcznie

Świadectwo wywozowe UE można utworzyć automatycznie za pomocą dokumentu dostawy na stronie **Wszystkie zamówienia sprzedaży** lub za pomocą faktury na stronie **Zamówienie sprzedaży**. Aby ręcznie utworzyć świadectwo wywozowe UE, można użyć faktury na stronie **Arkusz faktur**. Przed ręcznym utworzeniem świadectwa wywozowego UE trzeba jednak zmienić stan certyfikacji faktury.

### <a name="registering-an-eu-entry-certificate"></a>Rejestrowanie świadectwa wywozowego UE

Jeśli konieczna jest rejestracja, można też użyć strony **Arkusz świadectwa wywozowego**, aby zarejestrować świadectwo wywozowe UE wystawione przez inną firmę.

### <a name="uploading-a-received-eu-entry-certificate"></a>Przekazywanie odebranego świadectwa wywozowego UE

Aby przesłać odebrane świadectwo wywozowe UE podpisane przez odbiorcę z UE, użyj strony **Załączniki**. Po przesłaniu świadectwa, można skojarzyć je z fakturą jako dowód na dostarczenie towarów. Ten dowód jest wymagany, jeśli trzeba wystawić fakturę, która nie obejmuje podatku od towarów i usług (VAT), i jest też używany podczas inspekcji.

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a>Opcjonalnie: aktualizowanie stanu certyfikacji i drukowanie stanu faktury

Można zaktualizować stan świadectwa wywozowego i wydrukować stan faktury klienta za pomocą strony **Arkusz faktury**.

## <a name="technical-information-for-system-administrators"></a>Informacje techniczne dla administratorów systemu
Jeśli nie masz dostępu do stron, które są używane do ukończenia tego zadania, skontaktuj się z administratorem systemu i podaj informacje, które przedstawiono w poniższej tabeli.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategoria</th>
<th>Wymaganie wstępne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Role zabezpieczeń i obowiązki</td>
<td>Aby skonfigurować i utworzyć świadectwa wywozowe UE dla towarów lub usług, musisz być członkiem roli zabezpieczeń, która obejmuje następujące obowiązki:
<ul>
<li><strong>Pracownik ds. rozrachunków z odbiorcami</strong> (CustInvoiceAccountsReceivableClerk)</li>
<li><strong>Przedstawiciel obsługi klienta</strong> (TradeCustomerServiceRepresentative)</li>
<li><strong>Pracownik ds. sprzedaży</strong> (TradeSalesClerk)</li>
<li><strong>Pracownik ds. spedycji</strong> (InventShippingClerk)</li>
</ul></td>
</tr>
</tbody>
</table>





