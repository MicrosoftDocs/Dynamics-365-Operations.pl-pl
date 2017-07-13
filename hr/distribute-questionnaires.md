---
title: "Dystrybucja i wypełnianie kwestionariusza"
description: "W tym temacie opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: bcaaa846e0e88eca2c24048b483db8a031b19c43
ms.openlocfilehash: a8bbfd89d1bc34615e13b0cda62dcaf7c29e59eb
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Dystrybucja i wypełnianie kwestionariusza
<a id="distribute-and-complete-a-questionnaire" class="xliff"></a>

W tym temacie opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać. 

Istnieje wiele sposobów dystrybucji kwestionariusza:

-   Oznacz kwestionariusz jako aktywny. Kwestionariusz będzie dostępny dla wszystkich pracowników, chyba że ustawiono grupę kwestionariusza, która nie ma do niego dostępu.
-   Przypisz prawa grupie kwestionariusza. Kwestionariusz będzie dostępny dla wszystkich członków wybranej grupy.
-   Utwórz zaplanowane sesje odpowiedzi. Kwestionariusz będzie dostępny wyłącznie dla konkretnej osoby.
-   Utwórz harmonogram. Kwestionariusz można być dostępny dla wielu osób.

## Oznaczanie kwestionariusza jako aktywnego
<a id="marking-a-questionnaire-as-active" class="xliff"></a>
Ustawiając pole **Aktywne** jako **Tak** na stronie **Kwestionariusze**, można udostępnić kwestionariusz wszystkim pracownikom do wypełnienia. Respondenci mogą wypełnić kwestionariusz wiele razy. Ta funkcja jest przydatna do cyklicznego zbierania opinii przez cały rok. Na przykład można przygotować kwestionariusz dla pracowników, aby wyrazili opinię na temat jakości posiłków w stołówce zakładowej.

## Grupy kwestionariuszy
<a id="questionnaire-groups" class="xliff"></a>
Można ustawić grupy kwestionariusza i uwzględnić respondentów, do których należy przesłać kwestionariusz. 

Grupy kwestionariusza można utworzyć na następujących stronach:

-   **Grupy kwestionariuszy**— tylko osoby w grupie kwestionariusza mogą wypełnić wybrany kwestionariusz. Na przykład grupą docelową są kontrahenci, więc możesz utworzyć grupę kwestionariusza dla tych respondentów.
-   **Członkowie grupy kwestionariuszy** — do grup kwestionariuszy można dodawać osoby.

Aby przypisać grupę kwestionariusza do kwestionariusza, na stronie **Kwestionariusze** kliknij opcję **Prawa użytkownika**. Po zapisaniu kwestionariusza jako aktywny członkowie grupy kwestionariusza mogą wypełnić kwestionariusz. Ta funkcja jest przydatna do testowania kwestionariusza na wybranej grupie osób przed udostępnieniem go szerszej grupie respondentów lub kiedy chcesz skierować kwestionariusz do bardzo określonej grupy odbiorców.

## Planowane sesje odpowiedzi w kwestionariuszu
<a id="planned-answer-sessions-in-a-questionnaire" class="xliff"></a>
Zaplanowane sesje odpowiedzi to kwestionariusze, które zostały opracowane i wybrane dla respondentów. 

**Uwaga:** przed skonfigurowaniem zaplanowanych sesji odpowiedzi, należy zaprojektować kwestionariusz. 

Na stronie **Planowana sesja odpowiedzi** można utworzyć planowaną sesję odpowiedzi dla pojedynczego pracownika. Lista na tej stronie zawiera wszystkie zaplanowane kwestionariusze. 

Planowane sesje odpowiedzi są również używane na stronie **Harmonogramy kwestionariuszy**, gdzie można zaplanować kwestionariusze dla grup osób takich jak:

-   Pracownicy
-   Uczestnicy kursu
-   Jednostki organizacyjne

Każda osoba może wypełnić kwestionariusz tylko raz.

## Planowanie kwestionariusza
<a id="scheduling-a-questionnaire" class="xliff"></a>
Można opcjonalnie zaplanować kwestionariusz dla wielu respondentów.

### Typy planowania
<a id="planning-types" class="xliff"></a>

Typy planowania są wymagane, aby zaplanować zaplanowane sesje odpowiedzi dla wielu respondentów. Typy planowania są używane do klasyfikowania harmonogramów kwestionariuszy. Na przykład można ustalić harmonogram kwestionariuszy do następujących celów:

-   Ocena
-   Przegląd
-   Testowanie

Na stronie **harmonogramów kwestionariuszy** można określić typy planowania dla harmonogramu kwestionariusza.

### Typy odwołań do kwestionariusza
<a id="reference-types-for-questionnaire" class="xliff"></a>

Typy odwołań służą do wprowadzania kryteriów dla respondentów, które można wybrać podczas planowania kwestionariusza. 

Użyj strony **typy odwołań** do skonfigurowania odwołań do kwestionariusza. Każdy typ odwołania odpowiada tabeli w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Podczas tworzenia harmonogramów kwestionariuszy można określić poszczególne rekordy w tabeli lub zakres rekordów, które będzie można skojarzyć z kwestionariuszem. 

Na przykład zaznaczenie w tabeli kursów pozwala określić, do których kursów będzie się odnosić kwestionariusz. Po skonfigurowaniu odwołanie do tabeli kursów, niektóre pola i przyciski na stronie **kursów** stają się dostępne.

### Harmonogramy kwestionariuszy
<a id="questionnaire-schedules" class="xliff"></a>

Harmonogramy kwestionariuszy służą do generowania wielu planowanych sesji odpowiedzi dla grupy użytkowników, na podstawie typu odwołania. Utwórz harmonogram na stronie **Harmonogramy kwestionariuszy**. Wybierz typ planowania, aby skategoryzować harmonogram, a także wybierz typ odwołania, które powinno być używane do zapytań o konkretnych użytkowników systemu. Na przykład jeśli wybierzesz typ odwołania do tabeli kursów, możesz wybrać określony kurs w polu **Odwołanie**. 

Kliknij **Szczegóły ustawień**, aby wybrać kwestionariusz i inne kryteria. Na przykład można określić imię i nazwisko instruktora jako kryterium, jeśli kwestionariusz służy do oceny instruktora. Po zakończeniu wprowadzania szczegółów konfiguracji system generuje zaplanowane sesje odpowiedzi dla użytkowników, którzy są uwzględnieni w zapytaniu. 

Kliknij **Zaplanowane sesje odpowiedzi** w celu wyświetlania sesji odpowiedzi dla harmonogramu. Można ręcznie utworzyć dodatkowe planowane sesje odpowiedzi lub usunąć planowane sesje odpowiedzi, które nie otrzymały odpowiedzi. 

Kliknij kolejno opcje **Funkcje** &gt; **Start**, aby udostępnić kwestionariusz użytkownikom w powiązanych zaplanowanych sesjach odpowiedzi. Kliknij **Odpowiedzi** w celu wyświetlania odpowiedzi z wypełnionych kwestionariuszy. Opcjonalnie można skopiować ustawienia harmonogramu kwestionariusza, zaplanowanych sesji odpowiedzi i odpowiedzi do nowego harmonogramu kwestionariusza.

## Powiadamianie respondentów o kwestionariuszach, które są dla nich dostępne
<a id="notifying-respondents-about-questionnaires-that-are-available-to-them" class="xliff"></a>
Gdy rozprowadzasz kwestionariusz, musisz powiadomić respondentów, że kwestionariusze są dla nich dostępne. 

**Uwaga:** Respondenci muszą być użytkownikami programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, aby mogli wypełnić kwestionariusz.

### Powiadamianie respondentów o planowanej sesji odpowiedzi
<a id="notifying-respondents-about-a-planned-answer-session" class="xliff"></a>

Jeśli używasz planowanej sesji odpowiedzi, należy powiadomić wybraną osobę bezpośrednio, np. telefoniczne lub e-mailem.

### Powiadamianie respondentów o planowaniu
<a id="notifying-respondents-about-a-scheduling" class="xliff"></a>

Na stronie **Harmonogramy kwestionariuszy** można przygotować i wysłać wiadomość e-mail do wszystkich respondentów przypisanych do danego kwestionariusza. Wpisz tekst e-maila na karcie **Wiadomość e-mail samoobsługi pracownika**. Po rozpoczęciu harmonogramu kliknij kolejno opcje **Funkcje** &gt; **Wyślij wiadomość e-mail**, aby wygenerować i wysłać wiadomość e-mail do respondentów. Respondenci mogą następnie zalogować się w witrynie i wypełnić kwestionariusz. 

**Uwaga:** zanim będzie można skorzystać z funkcji poczty e-mail, administrator IT musi wprowadzić ustawienia poczty e-mail na stronie **Parametry poczty e-mail**.

## Kończenie planowanego arkusza
<a id="ending-a-scheduled-questionnaire" class="xliff"></a>
Można zakończyć zaplanowany kwestionariusz po ukończeniu przez wszystkich respondentów przypisanych do nich sesji odpowiedzi. Po zakończeniu zaplanowanego kwestionariusza, nie można skopiować jego ustawień do nowego harmonogramu. 

**Uwaga:** Jeśli co najmniej jeden respondent nie wypełnił kwestionariusza, a mimo to planowanie ma zostać zakończone, najpierw usuń odpowiednich respondentów z listy na stronie **Planowana sesja odpowiedzi**. Po wykonaniu tej czynności będzie można zakończyć planowanie.

## Wypełnianie kwestionariusza
<a id="completing-questionnaires" class="xliff"></a>
Po zaprojektowaniu i rozesłaniu kwestionariusza, kwestionariusz może zostać wypełniony przez wybranych respondentów. Kwestionariusze można wypełniać w dwóch lokalizacjach:

-   W okienku nawigacji kliknij kolejno opcje **Kwestionariusze** &gt; **Dystrybuuj** &gt; **Wypełnianie kwestionariusza**.
-   W obszarze Samoobsługa pracownika etatowego kliknij **Kwestionariusze do wypełnienia**.

Kwestionariusze można udostępnić wszystkich osobom w sieci, określonym użytkownikom lub grupom użytkowników.

Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Projektowanie kwestionariuszy](design-questionnaires.md)

[Używanie kwestionariuszy](questionnaires.md)

[Wyświetlanie i ocena wyników kwestionariuszy](evaluate-questionnaire-results.md)


