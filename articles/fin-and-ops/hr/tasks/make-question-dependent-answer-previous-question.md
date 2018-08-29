--- 
title: "Uzależnienie pytań od odpowiedzi na poprzednie pytanie"
description: "Pytania warunkowe umożliwiają określenie, jakie pytanie uzupełniające zostanie wyświetlone osobie udzielającej odpowiedzi na podstawie odpowiedzi na poprzednie pytanie."
author: ShylaThompson
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3e0a6d63a266bf49764c8cdcfd407ff0733ea27c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="make-questions-dependent-on-the-answer-of-the-previous-question"></a>Uzależnienie pytań od odpowiedzi na poprzednie pytanie

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pytania warunkowe umożliwiają określenie, jakie pytanie uzupełniające zostanie wyświetlone osobie udzielającej odpowiedzi na podstawie odpowiedzi na poprzednie pytanie. Na przykład jeśli zapytasz „Wolisz kawę czy herbatę”, logiczne pytanie uzupełniające można określić w zależności od tego, czy osoba udzielająca odpowiedzi wybierze kawę czy herbatę. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="find-the-existing-questionnaire"></a>Znajdowanie istniejącego kwestionariusza
1. Wybierz kolejno opcje Kwestionariusz > Projekt > Kwestionariusze.
2. Na liście zaznacz kwestionariusz WorkFH.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Dodawanie wszystkich pytań głównych i podrzędnych do kwestionariusza
1. Kliknij przycisk Pytania.
2. Kliknij przycisk Nowy.
3. W polu Pytanie wybierz pytanie numer 00016.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Ustawianie warunkowości sekwencji kwestionariusza i uzależnianie pytań od właściwych odpowiedzi
1. Kliknij przycisk Edytuj.
2. Rozwiń sekcję Ustawienia.
3. W polu Kolejność pytań wybierz opcję „Warunkowe”.
4. Kliknij opcję Pytanie warunkowe.
5. W drzewie zaznacz element „Pytania\Wyjaśnij powód udzielenia takiej a nie innej odpowiedzi na poprzednie pytanie.".
6. W polu Pytanie główne wybierz pytanie 00009.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Odpowiedź wprowadź identyfikator kolejności opcji odpowiedzi, od której ma zależeć pytanie. Na przykład wprowadź wartość 1 dla pierwszej opcji odpowiedzi.
9. Kliknij przycisk Zapisz.
10. W drzewie zaznacz element „Pytania\Otrzymuję uczciwe wynagrodzenie za wykonywaną pracę.”.
    * Należy zauważyć, że drzewo pytań zostało zaktualizowane w celu pokazania zależności.  


