---
title: Tworzenie pytania zamkniętego
description: Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8758b74f9ce7c8687b7c2925ccd04cd512602db0
ms.sourcegitcommit: 8246ba3872a1f3eaa18c8bb1ba86d3c2142a6e10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2021
ms.locfileid: "7465180"
---
# <a name="create-a-closed-ended-question"></a>Tworzenie pytania zamkniętego

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru. Najpierw należy utworzyć grupę odpowiedzi z odpowiedziami, a następnie pytanie, który będzie używało grupy odpowiedzi. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-an-answer-group"></a>Tworzenie grupy odpowiedzi
1. Wybierz kolejno opcje **Kwestionariusz** > **Projekt** > **Grupy odpowiedzi**.
2. Kliknij przycisk **Nowy**.
3. W polu **Grupa odpowiedzi** wpisz wartość.
4. W polu **Opis** wpisz wartość.
    * Funkcja Losowo spowoduje losowe rozmieszczanie odpowiedzi w różnej kolejności podczas każdorazowego użycia grupy odpowiedzi do pytania.  
5. Kliknij opcję **Odpowiedź**.
6. Kliknij przycisk **Nowy**.
    * Numer kolejny określa kolejność, w jakiej odpowiedzi są wyświetlane, chyba że dla grupy odpowiedzi wybrano opcję Losowo.  
    * Można przyznawać punkty za odpowiedzi z przeznaczeniem do wykorzystania przy ocenianiu wyników kwestionariusza.  
7. W polu **Punkty** wpisz liczbę.
    * Poprawną odpowiedź można oznaczyć, aby wskazać, że wybrana odpowiedź jest prawidłowa. To może służyć do oceniania wyników kwestionariusza.  
8. W polu **Odpowiedź** wpisz wartość.
    * Przejdź do tworzenia opcji wyboru odpowiedzi dla grupy odpowiedzi.  
9. Kliknij przycisk **Nowy**.
10. W polu **Punkty** wpisz liczbę.
11. W polu **Odpowiedź** wpisz wartość.
12. Kliknij przycisk **Nowy**.
13. W polu **Punkty** wpisz liczbę.
14. W polu **Odpowiedź** wpisz wartość.
15. Kliknij przycisk **Nowy**.
16. W polu **Punkty** wpisz liczbę.
17. W polu **Odpowiedź** wpisz wartość.
18. Kliknij przycisk **Nowy**.
19. W polu **Punkty** wpisz liczbę.
20. W polu **Odpowiedź** wpisz wartość.
21. Zamknij stronę.
22. Zamknij stronę.

## <a name="create-the-question"></a>Tworzenie pytania
1. Wybierz kolejno opcje **Kwestionariusz** > **Projekt** > **Pytania**.
2. Kliknij przycisk **Nowy**.
3. Pole Typ służy do grupowania powiązanych pytań.
    * Dla pytań zamkniętych można używać danych wejściowych typu pole wyboru, przycisk alternatywy lub pole kombi.  
4. W polu **Typ danych wejściowych** wybierz opcję.
5. W polu **Grupa odpowiedzi** wpisz lub wprowadź wartość.
6. W polu **Tekst** wpisz wartość.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
