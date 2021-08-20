---
title: Obsługa typów kodów kreskowych
description: W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania.
author: perlynne
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60fa8051ebe71c2606a5d6d3d1e22ec852023dd47301a008c98e9f4d7deaad29
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755365"
---
# <a name="maintain-barcode-types"></a>Obsługa typów kodów kreskowych

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości. Te zadania zazwyczaj wykonuje kierownik magazynu.

1. Przejdź do okna Kody kreskowe.
2. Kliknij przycisk Nowy.
3. W polu Konfiguracja kodów kreskowych wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ kodu kreskowego wybierz opcję.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać opcję „Kod 39”.  
6. W polu Rozmiar wpisz liczbę.
7. W polu Długość maksymalna wpisz liczbę.
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.
10. Przejdź do okna Parametry modułu Zarządzanie zapasami i magazynem.
11. W polu Konfiguracja kodów kreskowych wprowadź lub wybierz wartość.
    * Wybierz utworzoną wcześniej konfigurację kodu kreskowego, ale pamiętaj, że format kodu kreskowego musi być zgodny z formatem unikatowego identyfikatora typu rekordu używanego w procesie. Na przykład dla marszrut pobrania format kodu kreskowego musi być zgodny z formatem odwołania do marszruty pobrania, który jest zazwyczaj sekwencją numeracji.  
12. Kliknij przycisk Zapisz.
13. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]