---
title: Eksplorator źródeł księgowania
description: Ten artykuł zawiera informacje o stronie Eksplorator źródeł księgowania, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806441"
---
# <a name="accounting-source-explorer"></a>Eksplorator źródeł księgowania

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o stronie **Eksplorator źródeł księgowania**, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej.

**Eksplorator źródeł księgowania** to nowa strona, która pokazuje informacje o źródle. Możesz go używać jako samodzielnego narzędzia lub do analizy szczegółów zapisów księgowych księgi głównej. Na przykład możesz użyć strony, aby uzyskać najbardziej szczegółowe informacje o źródle salda w saldzie próbnym lub transakcji kuponu. Następnie za pomocą funkcji **eksportu do MS Excel** można dalej dzielić informacje w programie Microsoft Excel (na przykład w tabeli przestawnej lub raporcie tabeli przestawnej).

**Eksplorator źródeł księgowania** zawsze pokazuje tę samą sumę według konta księgowego co Księga główna (np. w bilansie próbnym). W bilansie próbnym można wyświetlić segmenty w osobnych kolumnach. Wystarczy zaznaczyć odpowiedni zestaw wymiarów finansowych. 

Za pomocą parametrów można zdefiniować interwał dat dla analizy. Ta funkcja przypomina też funkcję bilansu próbnego.

Dla wszystkich dokumentów, które używają struktury dokumentów źródłowych, **Eksplorator źródeł księgowania** zawiera dodatkowe informacje oparte o zasady podziału księgowań i (jeśli dotyczy) o zasady podziału księgowań dla projektu. Te informacje obejmują wartości **Typ kwoty pieniężnej**, **Projekt**, **Aktywność**, **Kategoria** i **Właściwość wiersza**. Oto kilka przykładów dostępnych analiz:

- Odchylenia między zamówieniami zakupu i fakturami od dostawcy, ponieważ każde odchylenie jest reprezentowane przez typ kwoty pieniężnej, np. odchylenie opłaty
- Rozliczane i nierozliczane godziny i wydatki według projektu, jednostki biznesowej i konta głównego

W przypadku dokumentów źródłowych korzystających z koncepcji tożsamości referencyjnych dokumentów źródłowych strona **Eksplorator źródeł księgowości** zawiera jeszcze więcej szczegółów, takich jak **Klient**, **Dostawca**, **Pracownik** , **Produkt**, **Ilość**, **Tekst jednostkowy** i **Opis**. Oto kilka przykładów dostępnych analiz:

- Wydatki na hotele na jednostkę biznesową i markę hotelu dla okresu obrachunkowego w oparciu o raporty z wydatków
- Rabaty na dostawcę, produkt, dział

W przypadku tych dokumentów Eksplorator źródeł księgowania pozwala też przejść do **Rzeczywistych dokumentów źródłowych**.

> [!NOTE]
> Od wersji 10.0.31 nowa funkcja **Zaawansowane filtrowanie Eksploratora źródeł księgowości** jest dostępna w zarządzaniu funkcjami. Ta funkcja zastępuje przycisk **Aktualizacja** , co zapewnia bardziej zaawansowane możliwości obsługi zapytań przypominające informacje dostępne na stronie **Transakcje na załączniku** . Filtr zaawansowany umożliwia filtrowanie według pól podobnych do tych, które można znaleźć na stronie **Zapytanie o transakcje kuponowe**, takie jak **Konto księgi**, **Jednostka biznesowa**, **Centrum kosztów** i **Dział**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
