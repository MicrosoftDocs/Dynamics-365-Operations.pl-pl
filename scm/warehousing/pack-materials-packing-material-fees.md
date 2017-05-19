---
title: "Materiały opakowaniowe i związane z nimi opłaty"
description: "Opłaty za materiały opakowań są uiszczane firmie recyklingowej w pewnych odstępach czasu. Płaci się kwotę według jednostki masy za każdy materiał, z którego jest wykonana jednostka opakowania. Opłaty za materiały opakowań są obliczane i zgłaszane, ale transakcje finansowe nie są księgowane, ponieważ opłaty nie są uznawane za podatki należne właściwemu organowi."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d8296dd0347a325a9ff3bd06f558d161ab4030dc
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="packing-materials-and-fees"></a>Materiały opakowaniowe i związane z nimi opłaty

[!include[banner](../includes/banner.md)]


Opłaty za materiały opakowań są uiszczane firmie recyklingowej w pewnych odstępach czasu. Płaci się kwotę według jednostki masy za każdy materiał, z którego jest wykonana jednostka opakowania. Opłaty za materiały opakowań są obliczane i zgłaszane, ale transakcje finansowe nie są księgowane, ponieważ opłaty nie są uznawane za podatki należne właściwemu organowi.

Wagi materiałów opakowań i opłaty są obliczane dla wierszy zamówienia sprzedaży i zakupu.

Istnieje możliwość zdefiniowania jednej lub wielu jednostek załadunkowych dla towaru, grupy opakowań towarów lub wszystkich towarów. W skład jednostki załadunkowej oprócz towarów, z których jednostka się składa, wchodzą różne materiały opakowań oraz ich wagi. Kod materiału opakowań jest przypisany do każdego zdefiniowanego typu materiału opakowania. Na podstawie kodu materiału opakowania można określić cenę w wybranym okresie. Opłata za materiały opakowań jest obliczana na podstawie tych informacji.

| **Uwaga**                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nawet jeśli firma nie uiszcza opłat materiałowych opakowań, można użyć tej funkcji do obliczania statystyk wag materiałów opakowań. |

## <a name="setup-requirements-for-packing-material-fees"></a>Wymagania konfiguracyjne dla opłat materiałowych opakowań
Przed obliczeniem wag materiałów opakowań i/lub opłat materiałowych opakowań, należy utworzyć następujące dane podstawowe:

-   Grupy opakowań — tworzenie grup opakowań do przypisania do towarów.
-   Kody materiałów opakowań — tworzenie kodów materiałów opakowań dla każdego zdefiniowanego typu materiału do pakowania.
-   Jednostki opakowania — określanie jednostki opakowania dla towaru, grupy opakowań lub wszystkich towarów. Dla każdej jednostki opakowania należy zdefiniować materiały opakowań, przypisać wagi i, w polu Współczynnik jednostki opakowania, wpisać współczynnik konwersji z jednostki zapasów.
-   Opłaty materiałowe opakowań — określanie opłat za materiały opakowań dla poszczególnych kodów materiałów opakowań. Dla każdego typu materiału należy zdefiniować okres ważności, cenę za materiał, walutę oraz jednostkę.

## <a name="packing-units-on-sales-order-lines"></a>Jednostki opakowań w wierszach zamówienia sprzedaży
W przypadku tworzenia wiersza zamówienia sprzedaży system sprawdza, czy jednostki opakowań są określone dla towaru. Jeśli określono jednostki opakowań, wiersz zamówienia sprzedaży jest aktualizowany w celu uwzględnienia określonej jednostki opakowań i liczby jednostek opakowań. Liczba jednostek opakowań jest opiera się na zamówionej ilości podzielonej przez liczbę towarów w wybranej jednostce opakowań. Jeśli jednostka opakowań nie została określona, można ręcznie wprowadzić jednostkę opakowań i liczbę jednostek opakowań w wierszu zamówienia sprzedaży. Istnieje również możliwość zmiany jednostki opakowań oraz liczby jednostek opakowań podczas księgowania wiersza zamówienia sprzedaży. Dotyczy to sytuacji, w której wiersz zamówienia sprzedaży jest tylko częściowo dostarczony lub częściowo zafakturowany. Po wystawieniu faktury na zamówienie sprzedaży tworzone są transakcje materiałów opakowań. Transakcje materiałów opakowań zawierają wagi materiałów opakowań w wierszu sprzedaży. Można także zmodyfikować transakcje po ich zafakturowaniu, a następnie utworzyć nowe transakcje.

## <a name="packing-units-on-purchase-order-lines"></a>Jednostki opakowań w wierszach zamówienia zakupu
Transakcje materiału opakowań dla wiersza zamówienia zakupu nie są tworzone przez system. Transakcje tworzy się ręcznie dla wierszy zafakturowanego zamówienia zakupu na stronie **Transakcje materiałów opakowań**.

## <a name="set-up-customer-packagingmaterialfee-license-numbers"></a>Konfigurowanie numerów licencji opłat za materiały opakowaniowe
Jeśli odbiorcy uiszczają opłaty materiałów opakowań, na stronie **Odbiorcy** należy określić numery licencji opłat materiałów opakowań dla odbiorców. Po przypisaniu numeru licencji do odbiorcy opłaty materiałów opakowań są obliczane automatycznie przy fakturowaniu zamówień sprzedaży. Po zafakturowaniu pole wyboru **Oblicz opłaty** na stronie **Transakcje materiałów opakowań** jest zaznaczone, ponieważ nie trzeba obliczać ani drukować raportu. Istnieje możliwość wydrukowania wag materiałów opakowań na fakturze oraz powiadomienia odbiorców o uiszczaniu opłat. 

Jeśli firma uiszcza opłaty materiałów opakowań, nie należy określać numerów licencji odbiorców. Po zafakturowaniu pole wyboru **Oblicz opłaty** na stronie **Transakcje materiałów opakowań** jest zaznaczone. To oznacza, że opłaty są obliczane w trakcie tworzenia raportu. Istnieje możliwość drukowania wag na fakturze oraz wskazywania, że firma uiszcza opłaty.

## <a name="print-packaging-material-weights-on-invoices"></a>Drukowanie wag materiałów opakowań na fakturach
Istnieje możliwość drukowania wag materiałów opakowań na fakturze oraz wskazywania podmiotów uiszczających opłaty materiałowe opakowań. Wagi zestawione są na podstawie kodu opakowania.
 





