--- 
title: "Tworzenie pytania zamkniętego"
description: "Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru."
author: kherr75
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fdfac92b80774adb8376d5c2e945d063173188c8
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-closed-ended-question"></a>Tworzenie pytania zamkniętego

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru. Najpierw należy utworzyć grupę odpowiedzi z odpowiedziami, a następnie pytanie, który będzie używało grupy odpowiedzi. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-an-answer-group"></a>Tworzenie grupy odpowiedzi
1. Wybierz kolejno opcje Kwestionariusz > Projekt > Grupy odpowiedzi.
2. Kliknij przycisk Nowy.
3. W polu Grupa odpowiedzi wpisz wartość.
4. Wypełnij pole Opis.
    * Funkcja Losowo spowoduje losowe rozmieszczanie odpowiedzi w różnej kolejności podczas każdorazowego użycia grupy odpowiedzi do pytania.  
5. Kliknij opcję Odpowiedź.
6. Kliknij przycisk Nowy.
    * Numer kolejny określa kolejność, w jakiej odpowiedzi są wyświetlane, chyba że dla grupy odpowiedzi wybrano opcję Losowo.  
    * Można przyznawać punkty za odpowiedzi z przeznaczeniem do wykorzystania przy ocenianiu wyników kwestionariusza.  
7. W polu Punkty wpisz liczbę.
    * Poprawną odpowiedź można oznaczyć, aby wskazać, że wybrana odpowiedź jest prawidłowa. To może służyć do oceniania wyników kwestionariusza.  
8. W polu Odpowiedź wpisz wartość.
    * Przejdź do tworzenia opcji wyboru odpowiedzi dla grupy odpowiedzi.  
9. Kliknij przycisk Nowy.
10. W polu Punkty wpisz liczbę.
11. W polu Odpowiedź wpisz wartość.
12. Kliknij przycisk Nowy.
13. W polu Punkty wpisz liczbę.
14. W polu Odpowiedź wpisz wartość.
15. Kliknij przycisk Nowy.
16. W polu Punkty wpisz liczbę.
17. W polu Odpowiedź wpisz wartość.
18. Kliknij przycisk Nowy.
19. W polu Punkty wpisz liczbę.
20. W polu Odpowiedź wpisz wartość.
21. Zamknij stronę.
22. Zamknij stronę.

## <a name="create-the-question"></a>Tworzenie pytania
1. Wybierz kolejno opcje Kwestionariusz > Projekt > Pytania.
2. Kliknij przycisk Nowy.
3. Pole Typ służy do grupowania powiązanych pytań.
    * Dla pytań zamkniętych można używać danych wejściowych typu pole wyboru, przycisk alternatywy lub pole kombi.  
4. W polu Typ danych wejściowych wybierz opcję.
5. W polu Grupa odpowiedzi wpisz lub wprowadź wartość.
6. W polu Tekst wpisz wartość.


