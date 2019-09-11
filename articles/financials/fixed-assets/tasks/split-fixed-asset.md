---
title: Rozbicie środka trwałego
description: W tym przewodniku po zadaniach jedna księga składników majatku zostanie podzielona procentowo w celu utworzenia nowej księgi składników majątku.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867590"
---
# <a name="split-a-fixed-asset"></a>Rozbicie środka trwałego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach jedna księga składników majatku zostanie podzielona procentowo w celu utworzenia nowej księgi składników majątku. Przewodnik wykorzystuje rolę Księgowy i dane firmy demonstracyjnej USMF.


## <a name="create-a-new-fixed-asset"></a>Umożliwia utworzenie nowego środka trwałego
1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.
2. Wybierz pozycję **Nowy**.
3. W polu **Grupa środków trwałych** wprowadź lub wybierz wartość. Zanotuj numer środka trwałego, ponieważ trzeba go będzie później wykorzystać w procesie podziału.  
4. W polu **Nazwa** wpisz wartość.
5. Zamknij formularz.

## <a name="split-a-fixed-asset"></a>Rozbicie środka trwałego
1. Na liście odszukaj i wybierz łącze środka trwałego, który ma zostać podzielony.
2. Wybierz **Księgi**. Wybierz księgę, która zostanie użyta w celu wydzielenia nowego składnika aktywów.  
3. Wybierz **Funkcje**.
4. Wybierz **Rozbicie środka trwałego**.
5. W polu **Do środka trwałego** wprowadź lub wybierz wartość.
6. W polu **Do księgi** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. W polu **Data transakcji** wprowadź datę.
8. W polu **Procent** wpisz liczbę.
9. Wprowadź lub wybierz wartość w polu **Nazwa arkusza**.
10. Kliknij przycisk **OK**.

## <a name="post-the-journal-transaction"></a>Księgowanie transakcji arkusza
1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.
2. Z listy wybierz arkusz utworzony za pomocą procesu podziału.
3. Wybierz **Linie**.

    - Sprawdź utworzone wiersze arkusza.  
    - Dla oryginalnego składnika aktywów jest tworzona transakcja korekty wartości początkowej, aby zmniejszyć wartość o procent określony w procesie podziału.  
    - Dla nowego składnika aktywów jest tworzona transakcja nabycia na tę samą kwotę.  

4. Wybierz opcję **Zaksięguj**.

