--- 
title: Generowanie planu z ograniczeniami
description: "W tej procedurze pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i zdolności produkcyjnych."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="generate-a-constrained-plan"></a>Generowanie planu z ograniczeniami

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i zdolności produkcyjnych. Plan gwarantuje, że produkcja nie rozpocznie się przed zapewnieniem dostępności materiałów i wyeliminowaniem ryzyka nadrezerwacji. 

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla planisty produkcji.


## <a name="set-up-a-constrained-plan"></a>Konfigurowanie planu z ograniczeniami
1. Kliknij opcję Planowanie główne.
2. Kliknij opcję Plany główne.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Przykład: Plan statyczny  
4. W polu Ograniczone zdolności produkcyjne wybierz opcję Tak.
5. W polu Horyzont czasowy ograniczonych zdolności produkcyjnych wpisz „30”.
6. Rozwiń sekcję Horyzonty czasowe w dniach.
7. W polu Zdolności produkcyjne wybierz opcję Tak.
8. W polu Horyzont czasowy planowania zdolności produkcyjnych wpisz liczbę dni.
    * Przykład: 60  
9. W polu Obliczone opóźnienia zaznacz opcję Tak.
10. W polu Oblicz horyzont czasowy opóźnień (dni) wpisz liczbę.
    * Przykład: 60  
11. Rozwiń sekcję Obliczone opóźnienia.
12. W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.
13. W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.
14. W polu Dodaj obliczone opóźnienie do daty zapotrzebowania zaznacz opcję Tak.
15. Zamknij stronę.

## <a name="create-a-constrained-plan"></a>Tworzenie planu z ograniczeniami
1. Kliknij przycisk Uruchom.
2. W polu Plan główny wprowadź lub wybierz wartość.
    * Zaznacz plan, dla którego skonfigurowano ograniczenia.  
3. Kliknij przycisk OK.
    * Może to trochę potrwać.  
4. Kliknij opcję Zamówienia planowane.


