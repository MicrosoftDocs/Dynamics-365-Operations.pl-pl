---
title: Format importu do konsolidacji
description: Ten temat zawiera szczegółowe informacje o formacie importu używanym podczas konsolidowania danych finansowych z wielu firm.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 714c34dfcd109a442a4ecd741409dea5c4aade20
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216813"
---
# <a name="import-format-for-consolidation"></a>Format importu do konsolidacji

[!include [banner](../includes/banner.md)]

Ten temat zawiera szczegółowe informacje o formacie importu używanym podczas konsolidowania danych finansowych z wielu firm. Format importu musi zostać zapisany jako plik tekstowy (txt).

## <a name="import-format"></a>Format importu

W poniższej tabeli wymieniono format importu, którego należy używać podczas konsolidacji podczas importu.

| Tabela rekordów | Format | Notatki |
|--------------|---------|-------|
| 1            | 170150, Goodwill, 4 | <ul><li>Tabela rekordów</li><li>Identyfikator źródłowego konta głównego</li><li>Wiersz konta głównego</li><li>Typ konta głównego</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>Identyfikator konta głównego</li><li>Data transakcji</li><li>Typ okresu obrachunkowego (**0** = Otwarcie, **1** = Operowanie i **2** = Zamknięcie)</li><li>Waluta transakcji</li><li>Debet lub kredyt (**0** = Debet i **1** = Kredyt)</li><li>Warstwa księgowania</li><li>Kwota transakcji</li><li>Ilość</li><li>Lokalny identyfikator RecID (niejednoznaczna, unikatowa wartość int64 dla transakcji)</li></ul> |
| 3            | USMF0000009, 2017-01-01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>Numer wpisu (numer transakcji nagłówka budżetu)</li><li>Domyślna data nagłówka budżetu</li><li>Identyfikator modelu budżetu</li><li>Typ budżeteu (**1** - budżet pierwotny, **2** - transfer, **3** - korekta, **4** - obciążenie, **5** - przed obciążeniem, **6** - budżet przeniesiony na późniejszy okres, **7** - projekt, **8** - aktywa stałe, **9** - prognoza popytu, **10** - prognoza podaży, **11** - przydziały, **12** - budżet wstępny.)</li><li>Data wiersza</li><li>Identyfikator konta głównego dla wiersza</li><li>Kod waluty płatności dla wiersza</li><li>Kwota dla wiersza w walucie transakcji</li><li>Wartość całkowita wyliczenia dla typu budżetu dla wiersza (wydatek lub przychód)</li></ul> |
| 4            | DEMF | RecordCompany jest firma źródłową. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>Identyfikator konta głównego</li><li>Data transakcji</li><li>Typ okresu obrachunkowego (0 Otwarcie, 1 Operowanie i 2 Zamknięcie)</li><li>Waluta transakcji</li><li>Debet lub kredyt (0 Debet i 1 Kredyt)</li><li>Warstwa księgowania</li><li>Kwota transakcji</li><li>Ilość</li><li>Lokalny identyfikator recid (niejednoznaczna, unikatowa wartość int64 dla transakcji)</li></ul>  |
| 6            | BusinessUnit, 1 Dział, 2 | Atrybuty wymiaru finansowego, które są zdefiniowane w kolejności segmentów.<p>Strona **Eksportuj** umożliwia sprawdzenie, jak są zdefiniowane atrybuty.</p> |
| 7            | 002,1,658 | <ul><li>Wartość wymiaru finansowego</li><li>Wymiar finansowy jako indeks dostarczany w RecordDimensions</li><li>Niejednoznaczny, niepowtarzalny identyfikator rekordu powiązany z unikalnym identyfikatorem rekordu z RecordTrans lub RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Wartości wymiarów skojarzone z transakcją z rekordu RecordBudget</li><li>Wymiar finansowy jako indeks dostarczany w RecordDimensions</li><li>Niejednoznaczny identyfikator rekordu wiersza, który jest zgodny z kolejnością wierszy transakcji w pliku</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
