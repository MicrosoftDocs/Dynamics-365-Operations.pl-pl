---
title: Opcje transakcji środków trwałych
description: W tym temacie opisano różne dostępne metody tworzenia transakcji na środkach trwałych.
author: ShylaThompson
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1857d68a0dfaa25386f19344e4cb3ddc9ffd39b8a75860a1642773d6bd59cce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764270"
---
# <a name="fixed-asset-transaction-options"></a>Opcje transakcji środków trwałych

[!include [banner](../includes/banner.md)]

W tym temacie opisano różne dostępne metody tworzenia transakcji na środkach trwałych.

Istnieje możliwość skonfigurowania modułu Środki trwałe w celu integracji z modułami Księga główna, Rozrachunki z dostawcami, Rozrachunki z odbiorcami i Zaopatrzenie i sourcing. Ponadto towary w module Zarządzanie zapasami można przenieść do modułu Środki trwałeh, aby można było używać tych towarów wewnętrznie.

## <a name="accounts-payable"></a>Rozrachunki z dostawcami
Istnieje możliwość wprowadzania transakcji środków trwałych na stronie Załącznik arkusza. Ta strona może być otwierana ze strony Arkusz faktur. Stronę załącznika arkusza można też otworzyć ze strony arkusza zatwierdzania faktur. W polu Typ konta przeciwstawnego wybierz Środki trwałe. Następnie w polu Konto przeciwstawne wybierz numer środka trwałego. Na karcie Środki trwałe wprowadź wartości w polach Typ transakcji i Księga.

## <a name="accounts-receivable"></a>Rozrachunki z odbiorcami
Istnieje możliwość wprowadzania transakcji środków trwałych na stronie Faktura niezależna.  Na stronie Faktura niezależna w siatce Wiersze faktury wybierz pozycję w wierszu. Kliknij skróconą kartę Szczegóły wiersza. Wprowadź numer środka trwałego i księgę dla transakcji likwidacji. W przypadku faktur niezależnych, transakcja środków trwałych jest zawsze typu Likwidacja — sprzedaż.

## <a name="procurement-and-sourcing"></a>Zaopatrzenie i sourcing
Istnieje możliwość wprowadzania transakcji środków trwałych na stronie Zamówienie zakupu. Wprowadź wymagane informacje, aby utworzyć zamówienie zakupu, a następnie kliknij OK. Na stronie zamówienia zakupu kliknij skróconą kartę Szczegóły wiersza. Następnie, na karcie Środki trwałe wprowadź informacje o środku trwałym. 

Aby zaksięgować transakcję nabycia istniejącego środka trwałego, należy określić numer środka trwałego, księgę i typ transakcji. Nie można zaksięgować środka trwałego, jeśli brakuje którejkolwiek z tych informacji. Aby zaksięgować transakcję nabycia nowego środka trwałego, zaznacz opcję Nowy środek trwały?, a następnie wybierz grupę środków trwałych, do której ma zostać przypisany nowy środek. Jednak nie są dostępne żadne pola środków trwałych dla wiersza, jeśli towar należy do grupy modeli magazynu, która używa modelu magazynu z kosztem standardowym. Ponadto, opcje, które są zdefiniowane na stronie Parametry środków trwałych, określają, czy można księgować transakcje nabycia z modułów zakupów. 

Jeśli do nabywania środków trwałych jest używany arkusz Zamówienie zakupu lub Środki trwałe z modułu Zapasy, ma to wpływ na wartość zapasów.

## <a name="general-ledger"></a>Księga główna
Transakcje środków trwałych dowolnego typu można księgować na stronie Arkusz finansowy. Można także używać arkuszy w module Środki trwałe, aby księgować transakcje środków trwałych.

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Opcje wprowadzania typów transakcji środków trwałych


| Typ transakcji                    | Moduł                   | Opcje                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Nabycie, korekta nabycia | Środki trwałe             | Środki trwałe, Zapasy do środków trwałych   |
|                                     | Księga główna           | Arkusze finansowe                           |
|                                     | Rozrachunki z dostawcami         | Arkusz faktury i arkusz zatwierdzania faktur |
|                                     | Zaopatrzenie i sourcing | Zamówienie zakupu                            |
| Amortyzacja                        | Środki trwałe             | Środki trwałe                              |
|                                     | Księga główna           | Arkusze finansowe                           |
| Likwidacja                            | Środki trwałe             | Środki trwałe                              |
| ** **                               | Księga główna           | Arkusze finansowe                           |
| ** **                               | Rozrachunki z odbiorcami      | Faktura niezależna                         |

Wartość pozostała Okresu amortyzacji środka trwałego nie jest aktualizowana, kiedy wiersz arkusza typu transakcji opisowej jest tworzony ręcznie lub importowany przez jednostkę danych. Ta wartość jest aktualizowana, kiedy proces propozycję amortyzacji jest używany do tworzenia wiersza arkusza.

Aby uzyskać więcej informacji, zobacz [Integracja środków trwałych](fixed-asset-integration.md).

### <a name="transactions-that-require-different-voucher-numbers"></a>Transakcje wymagające różnych numerów kuponów

Następujące transakcje dotyczące środków trwałych będą używać różnych numerów załączników:

- Nabycie dodatkowego składnika aktywów i efekcie obliczenie amortyzacji „wyrównującej”.
- Rozbicie środka trwałego.
- Włączenie parametru umożliwiającego obliczenie amortyzacji przy likwidacji, a następnie zlikwidowanie składnika aktywów.
- Data rozpoczęcia eksploatacji składnika aktywów jest wcześniejsza niż data nabycia. Z tego względu została zaksięgowana korekta amortyzacji.

> [!NOTE]
> Podczas wprowadzania transakcji należy się upewnić, że wszystkie transakcje mają zastosowanie do tego samego środka trwałego. Załącznik nie zostanie zaksięgowany, jeśli zawiera więcej niż jeden środek trwały, nawet jeśli pole **Nowy załącznik** ma wartość **Tylko jeden numer załącznika** na stronie **Nazwy arkuszy** w Księdze głównej. Jeśli dołączysz do załącznika więcej niż jeden środek trwały, otrzymasz komunikat „Może być tylko jedna transakcja środka trwałego na załącznik” i nie będzie można zaksięgować załącznika.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
