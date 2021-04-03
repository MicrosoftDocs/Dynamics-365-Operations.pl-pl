---
title: Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO
description: W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf196711799b78d7f4106b6693127d7f356b1d4e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262220"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Tworzenie typów zdobywania zamówień i kryteriów punktowania dla ZO

[!include [banner](../../includes/banner.md)]

W tym przewodniku pokazano, jak utworzyć typ zdobywania zamówień i skojarzyć go z metodą punktowania. Pokazano także sposób użycia typu zdobywania zamówień w zapytaniu ofertowym (ZO), w następstwie czego jest ustawiana domyślna metoda punktowania. Te zadania zazwyczaj wykonuje menedżer ds. zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem trzeba zapewnić dostępność metody punktowania.


## <a name="create-a-solicitation-type"></a>Tworzenie typu zdobywania zamówień
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zapytanie ofertowe > Typ zdobywania zamówień.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Metoda punktowa wybierz metodę punktowania, której chcesz używać dla tego typu zdobywania zamówień.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="use-the-solicitation-type"></a>Używanie typu zdobywania zamówień
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe.
2. Kliknij przycisk Nowy.
3. W polu Typ zdobywania zamówień wybierz nowo utworzony typ zdobywania zamówień. 
    *   
4. Kliknij przycisk OK.
5. Kliknij opcję Kryteria punktowania.
    * Wyświetlane kryteria punktowania pochodzą z metody punktowania skojarzonej z typem zdobywania zamówień. Na tej stronie można dodawać i usuwać kryteria. Istnieje również możliwość dodawania nowych kryteriów przez ich kopiowanie z innych metod punktowania.  
6. Kliknij opcję Kopiowanie kryteriów.
7. W polu Metoda punktowa wprowadź lub wybierz wartość.
8. Kliknij przycisk OK.
9. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]