---
title: Konfigurowanie siatek wynagrodzeń
description: Siatki wynagrodzeń są używane do definiowania i obsługi struktur płacy dla planów stałych wynagrodzeń.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0caebb2dfbff12545610aa6438dccbec84db3f9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190357"
---
# <a name="set-up-compensation-grids"></a>Konfigurowanie siatek wynagrodzeń

[!include [task guide banner](../../includes/task-guide-banner.md)]

Siatki wynagrodzeń są używane do definiowania i obsługi struktur płacy dla planów stałych wynagrodzeń. Siatki wynagrodzeń mogą być współużytkowane przez wiele planów lub kopiowane podczas tworzenia nowego planu wynagrodzeń.  Przed utworzeniem siatki wynagrodzeń należy skonfigurować poziomy i punkty odniesienia. W tym przykładzie zostanie utworzony nowy typ kategorii w siatce wynagrodzeń przy użyciu danych demonstracyjnych dla poziomów i punktów odniesienia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Konfigurowanie informacji o siatce wynagrodzeń
1. Wybierz kolejno opcje Zasoby ludzkie > Wynagrodzenia > Stałe wynagrodzenie > Siatki wynagrodzeń.
2. Kliknij przycisk Nowy.
3. W polu Siatka wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ wybierz opcję.
6. W polu Konfiguracja odniesienia wprowadź lub wybierz wartość.
7. W polu Waluta wprowadź lub wybierz wartość.
8. W polu Waluta wpisz wartość.
9. W polu Data obowiązywania wprowadź datę.

## <a name="add-levels-to-the-compensation-structure"></a>Dodawanie poziomów do struktury wynagrodzeń
1. Kliknij opcję Struktura wynagrodzeń.
2. Na liście oznacz wybrany wiersz.
3. W polu Poziom wprowadź lub wybierz wartość.
4. Kliknij przycisk Nowy.
5. Na liście oznacz wybrany wiersz.
6. W polu Poziom wprowadź lub wybierz wartość.
7. Kliknij przycisk Nowy.
8. Na liście oznacz wybrany wiersz.
9. W polu Poziom wprowadź lub wybierz wartość.
10. Kliknij przycisk Nowy.
11. Na liście oznacz wybrany wiersz.
12. W polu Poziom wprowadź lub wybierz wartość.
13. Kliknij przycisk Nowy.
14. Na liście oznacz wybrany wiersz.
15. W polu Poziom wprowadź lub wybierz wartość.

## <a name="fill-in-the-compensation-structure-with-values"></a>Wypełnianie struktury wynagrodzeń wartościami
1. Na liście oznacz wybrany wiersz.
    * W tym momencie wartości wynagrodzeń można ręcznie wprowadzić do każdego pola w tabeli lub użyć funkcji zmiany masowej i w jednym kroku łatwo wypełnić wiele pól oraz wykonać podstawowe obliczenia.  
2. Kliknij opcję Zmiana masowa.
    * W tej siatce najpierw zastosujemy wartość punktu środkowego pierwszego poziomu do wszystkich pól w tabeli. Będzie to podstawa macierzy wynagrodzeń.  
3. W polu Typ korekty wybierz opcję.
4. W polu Kwota korekty wpisz liczbę.
5. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
6. Kliknij przycisk Zastosuj do siatki.
    * Teraz użyjemy funkcji zmiany masowej, aby zwiększyć kwoty na każdym kolejnym poziomie o określony procent lub kwotę. W tym przykładzie rozpiętość między punktami środkowymi kategorii będzie wynosiła 12,5%.  
7. W polu Typ korekty wybierz opcję.
8. W polu Kwota korekty wpisz liczbę.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście znajdź i zaznacz odpowiedni rekord.
11. Na liście znajdź i zaznacz odpowiedni rekord.
12. Na liście znajdź i zaznacz odpowiedni rekord.
13. Kliknij przycisk Zastosuj do siatki.
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Na liście znajdź i zaznacz odpowiedni rekord.
17. Kliknij przycisk Zastosuj do siatki.
18. Na liście znajdź i zaznacz odpowiedni rekord.
19. Na liście znajdź i zaznacz odpowiedni rekord.
20. Kliknij przycisk Zastosuj do siatki.
21. Na liście znajdź i zaznacz odpowiedni rekord.
22. Kliknij przycisk Zastosuj do siatki.
    * Teraz użyjemy funkcji zmiany masowej, aby skorygować punkty odniesienia minimalny i maksymalny na każdym poziomie. W tym przykładzie zostanie użyta rozpiętość 50%, tak że minimalny punkt odniesienia zostanie skorygowany o -20%, a punkt maksymalny o +20%.  
23. W polu Kwota korekty wpisz liczbę.
24. W polu Punkt odniesienia wprowadź lub wybierz wartość.
25. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
26. Kliknij przycisk Zastosuj do siatki.
27. W polu Kwota korekty wpisz liczbę.
28. W polu Punkt odniesienia wprowadź lub wybierz wartość.
29. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
30. Kliknij przycisk Zastosuj do siatki.

