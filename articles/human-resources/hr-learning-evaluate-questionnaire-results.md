---
title: Wyświetlanie i ocenianie wyników kwestionariuszy
description: W tym temacie wyjaśniono, jak można wyświetlać i oceniać wyniki kwestionariuszy wypełnianych przez respondentów.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: d783664da957192575bbd2b1f0286243be190715
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688072"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>Wyświetlanie i ocenianie wyników kwestionariuszy


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie wyjaśniono, jak można wyświetlać i oceniać wyniki kwestionariuszy wypełnianych przez respondentów. 

Po wypełnieniu kwestionariusza przez respondentów można wyświetlić i ocenić wyniki na kilka sposobów:

-   **Zakończone sesje odpowiedzi** — wyświetlanie szczegółowych informacji dotyczących kwestionariuszy wypełnionych przez respondentów i generowanie raportów do podsumowania odpowiedzi i uzyskanych punktów.
-   **Grupy wyników** — wyświetlanie szczegółów grup wyników i statystyk kwestionariusza. Statystyki grupy wyników mogą być generowane dla sesji pojedynczej odpowiedzi kwestionariusza lub dla wszystkich sesji odpowiedzi.
-   **Statystyki kwestionariusza** — umożliwia określenie kryteriów do obliczania statystyk dla określonej grupy respondentów.

Można również generować różne raporty w celu wyświetlania wyników, które są sortowane według sesji odpowiedzi, osoby lub grupy wyników. Dostępne są następujące raporty, które są powiązane z wypełnionymi kwestionariuszami:

-   Odpowiedzi
-   Odpowiedzi na kwestionariusz
-   Odpowiedzi na osobę
-   Analiza informacji zwrotnych

## <a name="answer-session-results"></a>Wyniki sesji odpowiedzi

Kiedy respondenci wypełnią kwestionariusz, można wyświetlić wyniki zakończonych sesji odpowiedzi. Sesja odpowiedzi jest odpowiedzią jednego użytkownika na kwestionariusz. Umożliwia wyświetlenie szczegółowych informacji o sesji odpowiedzi na stronie **Odpowiedzi**. Sesje odpowiedzi, które są uwzględnione na stronie **Odpowiedzi** są filtrowane na różne sposoby, w zależności od tego, jak strona zostanie otwarta:

-   Wszystkie kwestionariusze
-   Wybrane kwestionariusze
-   Wybrana osoba

Na stronie **Odpowiedzi** można wyświetlić szczegóły dotyczące punktów uzyskanych, odpowiedzi respondenta w poszczególnych grupach wyników i hierarchii pytań, użytych w wybranym kwestionariuszu, jeśli użyto hierarchii pytań. Można również wygenerować i wydrukować następujące raporty:

-   **Raport wyników** — graficzna prezentacja uzyskanych punktów według grupy wyników dla wybranej sesji odpowiedzi.
-   **Raport odpowiedzi** — pokazuje odpowiedzi wybrane przez respondenta dla każdego pytania w kwestionariuszu.
-   **Niepoprawne odpowiedzi** — pokazuje informacje dotyczące nieprawidłowych odpowiedzi wybranych przez respondenta.

> [!NOTE]
> Strona **Wyniki** jest dostępna tylko w przypadku korzystania z grup wyników w kwestionariuszu i jeśli wybrano opcję **Strona wyników** na stronie **Kwestionariusze**. Strona **Odpowiedzi** oraz raport **Nieprawidłowe odpowiedzi** są dostępne tylko w przypadku wybrania opcji **Raport odpowiedzi** na stronie **Kwestionariusze**.

## <a name="questionnaire-statistics"></a>Statystyki kwestionariusza

Można użyć statystyk kwestionariusza do analizy wyników wypełnionego kwestionariusza na podstawie obliczeń zdefiniowanych przez użytkownika. Aby zdefiniować obliczenia, należy wykonać następujące zadania:

-   Wybierz kryteria obliczania i wyświetlania statystyk.
    -   Możesz wyświetlać statystyki według kwestionariusza, pytań, wierszy pytań lub grup wyników.
    -   Wybierz typ wykresu, który będzie używany podczas wyświetlania wyników.
    -   Wybierz typy osób z sieci, np. pracownicy, osoby kontaktowe lub kandydaci, których odpowiedzi mają zostać uwzględnione. Można również uwzględnić odpowiedzi z kwestionariuszy, które zostały wypełnione anonimowo.
    -   Skonfiguruj interwały opartych na wieku lub stażu do analizowania wyników.
-   Wymierz lub sprawdź poprawność ustawień, które precyzują zakres statysty. Na przykład wybierając kod pocztowy, można analizować wyniki dla wszystkich respondentów w konkretnym obszarze geograficznym.
-   Określ lub sprawdź poprawność kryteriów do analizy wyników według cech respondenta lub kwestionariusza. Na przykład, wybierając **kod pocztowy**, można analizować korelację między lokalizacją respondenta i poprawnymi odpowiedziami.

Ustawienia określone przez użytkownika są zapisywane i mogą być używane do okresowego ponownego obliczania wyników.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
