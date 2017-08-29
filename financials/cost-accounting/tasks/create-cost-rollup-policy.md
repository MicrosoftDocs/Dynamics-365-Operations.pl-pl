--- 
title: "Tworzenie zasady akumulacji kosztów"
description: "W tej procedurze pokazano, jak utworzyć zasadę akumulacji kosztów, a następnie reguły dla tej zasady."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 51fabc8fe17a45d104be5da806d7076bcf9c5dbb
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-cost-rollup-policy"></a>Tworzenie zasady akumulacji kosztów

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć zasadę akumulacji kosztów, a następnie reguły dla tej zasady. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.


## <a name="create-a-policy"></a>Tworzenie zasady
1. Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady akumulacji kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa zasad wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz centrum kosztów Akumulacja kosztów.  
6. W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz centrum kosztów Akumulacja kosztów.  
7. Kliknij przycisk Zapisz.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Tworzenie reguł dla zasady akumulacji kosztów
1. Kliknij przycisk Nowy.
2. Na liście oznacz wybrany wiersz.
3. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz pozycję 007.  
4. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz składnik kosztu Akumulacja kosztów.  
5. W polu Podrzędny składnik kosztu wprowadź lub wybierz wartość.
    * W tym przykładzie należy zamapować podrzędny składnik kosztu CC-007 na centrum kosztów.  
6. Kliknij przycisk Nowy.
7. Na liście oznacz wybrany wiersz.
8. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz pozycję 008.  
9. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz składnik kosztu Akumulacja kosztów.  
10. W polu Podrzędny składnik kosztu wprowadź lub wybierz wartość.
    * W tym przykładzie należy zamapować podrzędny składnik kosztu CC-008 na centrum kosztów.  
11. Kliknij przycisk Nowy.
12. Na liście oznacz wybrany wiersz.
13. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz pozycję 009.  
14. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz składnik kosztu Akumulacja kosztów.  
15. W polu Podrzędny składnik kosztu wprowadź lub wybierz wartość.
    * W tym przykładzie należy zamapować podrzędny składnik kosztu CC-009 na centrum kosztów.  
    * Kontynuuj, aż wszystkie centra kosztów zostaną zamapowane na ich odnośne podrzędne składniki kosztów.  
16. Kliknij przycisk Zapisz.


