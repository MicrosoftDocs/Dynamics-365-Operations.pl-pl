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
ms.openlocfilehash: 052311e15aeb20b927cbed217a2bda600dad60a5
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345657"
---
# <a name="maintain-bar-code-types"></a>Obsługa typów kodów kreskowych

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób konfigurowania nowej definicji kodu kreskowego, która następnie może służyć jako część raportu listy pobrania. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości. Te zadania zazwyczaj wykonuje kierownik magazynu.

1. Przejdź do okna **Kody kreskowe**.
1. Wybierz pozycję **Nowy**.
1. W polu **Konfiguracja kodów kreskowych** wpisz wartość.
1. W polu **Opis** wpisz wartość.
1. W polu **Typ kodu kreskowego** wybierz opcję.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać opcję „Kod 39”.  
1. W polu **Rozmiar** wpisz liczbę.
1. W polu **Długość maksymalna** wpisz liczbę.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.
1. Przejdź do okna **Parametry modułu Zarządzanie zapasami i magazynem**.
1. W polu **Konfiguracja kodów kreskowych** wprowadź lub wybierz wartość.
    * Wybierz utworzoną wcześniej konfigurację kodu kreskowego, ale pamiętaj, że format kodu kreskowego musi być zgodny z formatem unikatowego identyfikatora typu rekordu używanego w procesie. Na przykład dla marszrut pobrania format kodu kreskowego musi być zgodny z formatem odwołania do marszruty pobrania, który jest zazwyczaj sekwencją numeracji.  
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]