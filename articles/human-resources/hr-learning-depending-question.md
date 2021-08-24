---
title: Uzależnienie pytania od odpowiedzi na poprzednie pytanie
description: Pytania warunkowe umożliwiają określenie, jakie pytanie uzupełniające zostanie wyświetlone osobie udzielającej odpowiedzi na podstawie odpowiedzi na poprzednie pytanie.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9397b3dfa353398a5d326ae68ec8269369ebf85b7b2e61c73013db76c5dd475
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745701"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Uzależnienie pytania od odpowiedzi na poprzednie pytanie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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



[!INCLUDE[footer-include](../includes/footer-banner.md)]