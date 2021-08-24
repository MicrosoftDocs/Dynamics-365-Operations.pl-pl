---
title: Analizowanie wyników kwestionariusza
description: Statystyki kwestionariusza mogą służyć do obliczania wartości średnich, sum i wartości procentowych na podstawie zbioru danych demograficznych.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c61fa41f5502750c07e773568e65cc03df86fa6af4878de7d2c956317a15d495
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724995"
---
# <a name="analyzing-questionnaire-results"></a>Analizowanie wyników kwestionariusza

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Statystyki kwestionariusza mogą służyć do obliczania wartości średnich, sum i wartości procentowych na podstawie zbioru danych demograficznych. Aby rozpocząć tę procedurę, wybierz kolejno opcje Kwestionariusz > Wyświetl i analizuj wyniki > Statystyki kwestionariusza. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-questionnaire-statistics-record"></a>Tworzenie rekordu statystyk kwestionariusza
1. Przejdź do okna Statystyki kwestionariusza.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Statystyki wpisz wartość.
5. W polu Opis wpisz wartość.
6. W polu Kwestionariusz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście kliknij łącze w wybranym wierszu.
8. Kliknij kartę Ogólne.
    * Wskaż, czy chcesz uwzględniać wyniki anonimowe czy wyniki od pracowników, osób kontaktowych i kandydatów.  
9. Zaznacz lub wyczyść pole wyboru Pracownik.
    * Jeśli będziesz oglądać wyniki według stażu pracy lub wieku, określ interwały, których chcesz używać do grupowania wyników.  
    * Wprowadzenie wartości 5 dla okresu wieku spowoduje grupowanie wyników w oparciu o pięcioletnie interwały wieku.  
10. W polu Wiek wpisz liczbę.
    * Wskaż, czy chcesz wykonać obliczenie dla całego kwestionariusza, dla każdej grupy wyników, dla każdego pytania czy dla każdego wiersza pytań.  
    * Określ, jak chcesz grupować wyniki.  
    * Na przykład przy obliczaniu średniej liczby punktów na pytanie warto oglądać pytania pogrupowane według grup wyników.  
    * Zaznacz dane, które będą podstawą obliczeń.  
    * Na przykład jeśli chcesz zobaczyć średni procent uzyskiwany w kwestionariuszu przez pracowników w porównaniu ze średnią liczba punktów osiąganą przez pracowników.  
11. Kliknij kartę Zakres.
    * Użyj zakresów, aby ograniczyć zestaw wyników tylko do tych spełniających kryteria zakresu.  
12. Kliknij kartę Grupowanie wg.
    * Za pomocą grup określ sposób wyświetlania wyników.  
    * Na przykład pogrupuj wyniki najpierw według płci, a następnie według wieku.  
13. Na liście znajdź i zaznacz odpowiedni rekord.
    * Przenieś grupy na stronę Wybrane i umieść je w żądanej kolejności.  

## <a name="execute-the-statistics-calculation"></a>Obliczanie statystyk
1. Kliknij przycisk Wykonaj.
    * Wybierz funkcję obliczania, którą chcesz zastosować do wyników.  
    * Na przykład oblicz średnie wartości procentowe z kwestionariusza dla wybranej grupy lub sumy punktów w grupach wyników dla wybranych grup.  
2. Zaznacz lub wyczyść pole wyboru Usuwanie poprzednich wyszukiwań.
3. Kliknij przycisk OK.

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>Służy do wyświetlania wyników sesji statystyk kwestionariusza.
1. Kliknij przycisk Wynik.
2. Kliknij przycisk Wynik.
3. Zamknij stronę.



[!INCLUDE[footer-include](../includes/footer-banner.md)]