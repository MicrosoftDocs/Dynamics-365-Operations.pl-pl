--- 
title: "Rozbicie środka trwałego"
description: "W tym przewodniku po zadaniach jedna księga środków trwałych zostanie podzielona procentowo w celu utworzenia nowej księgi środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5aea1aab9f6b084bd0c5bd2119639bff3555bb8a
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="split-a-fixed-asset"></a>Rozbicie środka trwałego

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach jedna księga środków trwałych zostanie podzielona procentowo w celu utworzenia nowej księgi środków trwałych.  Przewodnik wykorzystuje rolę Księgowy i dane firmy demonstracyjnej USMF.


## <a name="create-a-new-fixed-asset"></a>Utwórz nowy środek trwały
1. Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.
2. Kliknij przycisk Nowy.
3. W polu Grupa środków trwałych wprowadź lub wybierz wartość.
4. Zanotuj numer środka trwałego, ponieważ trzeba go będzie później wykorzystać w procesie podziału.
5. W polu Nazwa wpisz wartość.
6. Zamknij formularz.

## <a name="split-a-fixed-asset"></a>Rozbicie środka trwałego
1. Na liście odszukaj i zaznacz środek trwały, który ma zostać podzielony.
2. Na liście kliknij łącze w wybranym wierszu.
3. Kliknij opcję Księgi.
    * Wybierz księgę, która zostanie użyta w celu wydzielenia nowego składnika aktywów.  
4. Kliknij przycisk Funkcje.
5. Kliknij opcję Rozbicie środka trwałego.
6. W polu Do środka trwałego wprowadź lub wybierz wartość.
7. W polu Do księgi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. W polu Data transakcji wprowadź datę.
9. W polu Procent wpisz liczbę.
10. Wprowadź lub wybierz wartość w polu Nazwa arkusza.
11. Kliknij przycisk OK.

## <a name="post-the-journal-transaction"></a>Księgowanie transakcji arkusza
1. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.
2. Z listy wybierz arkusz utworzony za pomocą procesu podziału.
3. Kliknij przycisk Wiersze.
    * Sprawdź utworzone wiersze arkusza.  Dla oryginalnego składnika aktywów jest tworzona transakcja korekty wartości początkowej, aby zmniejszyć wartość o procent określony w procesie podziału.  Dla nowego składnika aktywów jest tworzona transakcja nabycia na tę samą kwotę.  
4. Kliknij przycisk Księguj.


