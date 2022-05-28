---
title: Obliczanie amortyzacji środka trwałego we wszystkich firmach
description: Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku.
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ca54a45b81b66fdcdd5e43ad6b8c408cb764fb9
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712126"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Obliczanie amortyzacji środka trwałego we wszystkich firmach

[!include [banner](../../includes/banner.md)]

Amortyzację środków trwałych można uruchomić w wielu firmach w jednym kroku. Ta procedura przedstawia sposób ustawiania i uruchamiania procesu dla wielu firm. Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Ustawianie arkuszy uruchomienia amortyzacji w całej firmie
1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Parametry środków trwałych.
2. Rozwiń sekcję Propozycje środków trwałych.
3. Kliknij przycisk Dodaj.
4. W polu Warstwa księgowania wprowadź lub wybierz wartość.
5. Wprowadź lub wybierz wartość w polu Nazwa arkusza.
    * Powtórz ustawianie arkusza na stronie Parametry środków trwałych w każdej firmie.  

## <a name="depreciation-run"></a>Uruchomienie amortyzacji
1. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.
2. W polu Warstwa księgowania wprowadź lub wybierz wartość.
    * Nazwa arkusza przyjmie wartość domyślną z parametrów środków trwałych. Można ją zmienić tutaj dla bieżącej firmy.  
3. Wprowadź datę w polu Do dnia.
    * Wybierz firmy, które mają zostać uwzględnione w uruchomieniu amortyzacji.  
    * Na liście będą widoczne tylko firmy z arkuszami ustawionymi dla propozycji środków trwałych na stronie Parametry środków trwałych.  
4. Wybierz opcję Tak w polu Zaksięguj arkusze.
    * Pola filtrowania obejmują wszystkie środki trwałe, grupy i księgi dla firm wybranych do tego uruchomienia amortyzacji.  
    * Opcja Przetwarzanie wsadowe jest domyślnie włączona. Gdy ta opcja jest włączona, tworzenie i księgowanie arkusza amortyzacji zostanie uruchomione w tle.  
5. Kliknij opcję Utwórz arkusz.
6. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
