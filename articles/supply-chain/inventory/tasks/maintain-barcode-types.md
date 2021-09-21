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
ms.openlocfilehash: 4102f8036c0aede7c8a2adcaa9b8799a71ac7ada
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2021
ms.locfileid: "7441296"
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
1. W polu **Identyfikator maski** określ identyfikator maski kodu kreskowego. Maski kodów kreskowych są używane do tworzenia kodów kreskowych i do szybkiej identyfikacji kodów kreskowych skanowanych w systemie punktu sprzedaży (POS). Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie masek kodów kreskowych](../../../commerce/set-up-bar-code-masks.md).
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
