---
title: Określanie sposobu likwidacji zwróconych towarów
description: Można określić sposób likwidacji zwróconych towarów.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 61bff50d55ed4c251918a327f2a033369e731bf0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242380"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>Określanie sposobu likwidacji zwróconych towarów 

[!include [banner](../includes/banner.md)]


Podczas obsługi zamówienia zwrotu należy określić kod przyczyny zwrotu wskazujący powód zwracania produktu. Należy także określić kod dyspozycji i akcję dyspozycji, aby określić, co należy zrobić ze zwracanym produktem.

Kod dyspozycji można zastosować po utworzeniu zamówienia zwrotu, zarejestrowaniu przyjęcia towaru lub zaktualizowaniu dokumentu dostawy dla przyjęcia towaru oraz zakończeniu zlecenia kwarantanny.

Można definiować dowolne kody dyspozycji potrzebne w celu obsługi procesów biznesowych. W poniższej tabeli przedstawiono zestaw często używanych kodów służących do przypisywania dyspozycji zwrotu towaru.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Typ dyspozycji</p></th>
<th><p>Typowy kod</p></th>
<th><p>opis</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Likwidacja</p></td>
<td><p>LZ</p></td>
<td><p>Likwidacja/zniszczenie</p></td>
</tr>
<tr class="even">
<td><p>Likwidacja</p></td>
<td><p>PCD</p></td>
<td><p>Przekazanie na cele dobroczynne</p></td>
</tr>
<tr class="odd">
<td><p>Likwidacja</p></td>
<td><p>LFZ</p></td>
<td><p>Likwidacja przez firmę zewnętrzną</p></td>
</tr>
<tr class="even">
<td><p>Likwidacja</p></td>
<td><p>OD</p></td>
<td><p>Odzysk</p></td>
</tr>
<tr class="odd">
<td><p>Likwidacja</p></td>
<td><p>SFZ</p></td>
<td><p>Sprzedaż przez firmę zewnętrzną (rynki wtórne)</p></td>
</tr>
<tr class="even">
<td><p>Naprawa/modyfikacja</p></td>
<td><p>PR</p></td>
<td><p>Przeróbka</p></td>
</tr>
<tr class="odd">
<td><p>Naprawa/modyfikacja</p></td>
<td><p>PPO</p></td>
<td><p>Ponowna produkcja/odnowienie</p></td>
</tr>
<tr class="even">
<td><p>Naprawa/modyfikacja</p></td>
<td><p>MD</p></td>
<td><p>Modyfikacja</p></td>
</tr>
<tr class="odd">
<td><p>Naprawa/modyfikacja</p></td>
<td><p>NP</p></td>
<td><p>Naprawa</p></td>
</tr>
<tr class="even">
<td><p>Naprawa/modyfikacja</p></td>
<td><p>ZD</p></td>
<td><p>Zwrot do dostawcy</p></td>
</tr>
<tr class="odd">
<td><p>Inne</p></td>
<td><p>UOP</p></td>
<td><p>Zastosowanie w obecnej postaci</p></td>
</tr>
<tr class="even">
<td><p>Inne</p></td>
<td><p>OS</p></td>
<td><p>Odsprzedaż</p></td>
</tr>
<tr class="odd">
<td><p>Inne</p></td>
<td><p>WM</p></td>
<td><p>Import/eksport</p></td>
</tr>
<tr class="even">
<td><p>Inne</p></td>
<td><p>RN</p></td>
<td><p>Różne</p></td>
</tr>
</tbody>
</table>


Dla każdego zdefiniowanego kodu dyspozycji musisz wybrać akcję dyspozycji. Akcja dyspozycji określa fizyczne i finansowe następstwa kodów dyspozycji. Na przykład akcja dyspozycji określa fizyczną obsługę zwróconego towaru, skutek finansowy zwrotu towarów i czy towar zastępczy musi zostać wysłany do odbiorcy. Można zdefiniować nieograniczoną liczbę kodów dyspozycji zależnie od potrzeb biznesowych, ale są tylko sześć wstępnie zdefiniowanych akcji dyspozycji, z których można wybierać. Poniższa tabela zawiera akcje dyspozycji i ich definicje.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Akcja dyspozycji</p></th>
<th><p>opis</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Strona kredytowa</strong></p></td>
<td><p>Zwracanie towaru do magazynu i kredyt dla odbiorcy.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tylko kredytowe</strong></p></td>
<td><p>Kredyt dla odbiorcy bez wymagań lub oczekiwań zwrotu towaru.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Odpadki</strong></p></td>
<td><p>Uznanie towaru za odpad i kredyt dla odbiorcy.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zastąp i zaksięguj po stronie kredytowej</strong></p></td>
<td><p>Zwraca towar do magazynu, tworzenie zamówienie wymiany i kredyt dla odbiorcy.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zastąp i zlikwiduj</strong></p></td>
<td><p>Przeznaczenie towaru na odpadki, tworzenie zamówienia wymiany i kredyt dla odbiorcy.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zwrot do odbiorcy</strong></p></td>
<td><p>Odrzucenie zwróconego towaru i zwrócenie go do odbiorcy.</p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Wybieranie kodu dyspozycji dla zlecenia kwarantanny

1.  Kliknij kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Zarządzanie jakością** \> **Zlecenia kwarantanny**.

2.  Dla istniejącego zlecenia kwarantanny wybierz akcję w polu **Kod dyspozycji** na karcie **Przegląd**.



## <a name="see-also"></a>Informacje dodatkowe

[Zlecenie kwarantanny (formularz)](https://technet.microsoft.com/library/aa554073(v=ax.60))

[Kody dyspozycji (formularz)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]