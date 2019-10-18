---
title: Rozprowadzanie i planowanie kwestionariuszy
description: W tym temacie opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e0369be278519f39fc304b34ef3a270438f0bb1
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026263"
---
# <a name="distribute-and-schedule-questionnaires"></a>Rozprowadzanie i planowanie kwestionariuszy

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać. 

Istnieje wiele sposobów dystrybucji kwestionariusza:

-   Oznacz kwestionariusz jako aktywny. Kwestionariusz będzie dostępny dla wszystkich pracowników, chyba że ustawiono grupę kwestionariusza, która nie ma do niego dostępu.
-   Przypisz prawa grupie kwestionariusza. Kwestionariusz będzie dostępny dla wszystkich członków wybranej grupy.
-   Utwórz zaplanowane sesje odpowiedzi. Kwestionariusz będzie dostępny wyłącznie dla konkretnej osoby.
-   Utwórz harmonogram. Kwestionariusz można być dostępny dla wielu osób.

## <a name="marking-a-questionnaire-as-active"></a>Oznaczanie kwestionariusza jako aktywnego
Ustawiając pole **Aktywne** jako **Tak** na stronie **Kwestionariusze**, można udostępnić kwestionariusz wszystkim pracownikom do wypełnienia. Respondenci mogą wypełnić kwestionariusz wiele razy. Ta funkcja jest przydatna do cyklicznego zbierania opinii przez cały rok. Na przykład można przygotować kwestionariusz dla pracowników, aby wyrazili opinię na temat jakości posiłków w stołówce zakładowej.

## <a name="questionnaire-groups"></a>Grupy kwestionariuszy
Można ustawić grupy kwestionariusza i uwzględnić respondentów, do których należy przesłać kwestionariusz. 

Grupy kwestionariusza można utworzyć na następujących stronach:

-   **Grupy kwestionariuszy**— tylko osoby w grupie kwestionariusza mogą wypełnić wybrany kwestionariusz. Na przykład grupą docelową są kontrahenci, więc możesz utworzyć grupę kwestionariusza dla tych respondentów.
-   **Członkowie grupy kwestionariuszy** — do grup kwestionariuszy można dodawać osoby.

Aby przypisać grupę kwestionariusza do kwestionariusza, na stronie **Kwestionariusze** kliknij opcję **Prawa użytkownika**. Po zapisaniu kwestionariusza jako aktywny członkowie grupy kwestionariusza mogą wypełnić kwestionariusz. Ta funkcja jest przydatna do testowania kwestionariusza na wybranej grupie osób przed udostępnieniem go szerszej grupie respondentów lub kiedy chcesz skierować kwestionariusz do bardzo określonej grupy odbiorców.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Planowane sesje odpowiedzi w kwestionariuszu
Zaplanowane sesje odpowiedzi to kwestionariusze, które zostały opracowane i wybrane dla respondentów. 

> **Uwaga:** Przed skonfigurowaniem zaplanowanych sesji odpowiedzi należy zaprojektować kwestionariusz. 

Na stronie **Planowana sesja odpowiedzi** można utworzyć planowaną sesję odpowiedzi dla pojedynczego pracownika. Lista na tej stronie zawiera wszystkie zaplanowane kwestionariusze. 

Planowane sesje odpowiedzi są również używane na stronie **Harmonogramy kwestionariuszy**, gdzie można zaplanować kwestionariusze dla grup osób takich jak:

-   Pracownicy
-   Uczestnicy kursu
-   Jednostki organizacyjne

Każda osoba może wypełnić kwestionariusz tylko raz.

## <a name="scheduling-a-questionnaire"></a>Planowanie kwestionariusza
Można opcjonalnie zaplanować kwestionariusz dla wielu respondentów.

### <a name="planning-types"></a>Typy planowania

Typy planowania są wymagane, aby zaplanować zaplanowane sesje odpowiedzi dla wielu respondentów. Typy planowania są używane do klasyfikowania harmonogramów kwestionariuszy. Na przykład można ustalić harmonogram kwestionariuszy do następujących celów:

-   Ocena
-   Przegląd
-   Testowanie

Na stronie **harmonogramów kwestionariuszy** można określić typy planowania dla harmonogramu kwestionariusza.

### <a name="reference-types-for-questionnaire"></a>Typy odwołań do kwestionariusza

Typy odwołań służą do wprowadzania kryteriów dla respondentów, które można wybrać podczas planowania kwestionariusza. 

Użyj strony **typy odwołań** do skonfigurowania odwołań do kwestionariusza. Każdy typ odwołania odpowiada tabeli w Microsoft Dynamics 365 Finance. Podczas tworzenia harmonogramów kwestionariuszy można określić poszczególne rekordy w tabeli lub zakres rekordów, które będzie można skojarzyć z kwestionariuszem. 

Na przykład zaznaczenie w tabeli kursów pozwala określić, do których kursów będzie się odnosić kwestionariusz. Po skonfigurowaniu odwołanie do tabeli kursów, niektóre pola i przyciski na stronie **kursów** stają się dostępne.

### <a name="questionnaire-schedules"></a>Harmonogramy kwestionariuszy

Harmonogramy kwestionariuszy służą do generowania wielu planowanych sesji odpowiedzi dla grupy użytkowników, na podstawie typu odwołania. Utwórz harmonogram na stronie **Harmonogramy kwestionariuszy**. Wybierz typ planowania, aby skategoryzować harmonogram, a także wybierz typ odwołania, które powinno być używane do zapytań o konkretnych użytkowników systemu. Na przykład jeśli wybierzesz typ odwołania do tabeli kursów, możesz wybrać określony kurs w polu **Odwołanie**. 

Kliknij **Szczegóły ustawień**, aby wybrać kwestionariusz i inne kryteria. Na przykład można określić imię i nazwisko instruktora jako kryterium, jeśli kwestionariusz służy do oceny instruktora. Po zakończeniu wprowadzania szczegółów konfiguracji system generuje zaplanowane sesje odpowiedzi dla użytkowników, którzy są uwzględnieni w zapytaniu. 

Kliknij **Zaplanowane sesje odpowiedzi** w celu wyświetlania sesji odpowiedzi dla harmonogramu. Można ręcznie utworzyć dodatkowe planowane sesje odpowiedzi lub usunąć planowane sesje odpowiedzi, które nie otrzymały odpowiedzi. 

Kliknij kolejno opcje **Funkcje** &gt; **Start**, aby udostępnić kwestionariusz użytkownikom w powiązanych zaplanowanych sesjach odpowiedzi. Kliknij **Odpowiedzi** w celu wyświetlania odpowiedzi z wypełnionych kwestionariuszy. Opcjonalnie można skopiować ustawienia harmonogramu kwestionariusza, zaplanowanych sesji odpowiedzi i odpowiedzi do nowego harmonogramu kwestionariusza.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Powiadamianie respondentów o kwestionariuszach, które są dla nich dostępne
Gdy rozprowadzasz kwestionariusz, musisz powiadomić respondentów, że kwestionariusze są dla nich dostępne. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Powiadamianie respondentów o planowanej sesji odpowiedzi

Jeśli używasz planowanej sesji odpowiedzi, należy powiadomić wybraną osobę bezpośrednio, np. telefoniczne lub e-mailem.

### <a name="notifying-respondents-about-a-scheduling"></a>Powiadamianie respondentów o planowaniu

Na stronie **Harmonogramy kwestionariuszy** można przygotować i wysłać wiadomość e-mail do wszystkich respondentów przypisanych do danego kwestionariusza. Wprowadź tekst wiadomości e-mail na karcie **Wiadomość e-mail samoobsługi pracownika**. Po rozpoczęciu harmonogramu kliknij opcję **Funkcje** &gt; **Wyślij wiadomość e-mail**, aby wygenerować i wysłać wiadomość e-mail do osób udzielających odpowiedzi. Respondenci mogą następnie zalogować się w witrynie i wypełnić kwestionariusz. 

> **Uwaga:** Zanim będzie można skorzystać z funkcji poczty e-mail, administrator IT musi wprowadzić ustawienia poczty e-mail na stronie **Parametry poczty e-mail**.

## <a name="ending-a-scheduled-questionnaire"></a>Kończenie planowanego arkusza
Można zakończyć zaplanowany kwestionariusz po ukończeniu przez wszystkich respondentów przypisanych do nich sesji odpowiedzi. Po zakończeniu zaplanowanego kwestionariusza, nie można skopiować jego ustawień do nowego harmonogramu. 

> **Uwaga:** Jeśli co najmniej jeden respondent nie wypełnił kwestionariusza, a mimo to planowanie ma zostać zakończone, najpierw usuń odpowiednich respondentów z listy na stronie **Planowana sesja odpowiedzi**. Po wykonaniu tej czynności będzie można zakończyć planowanie.

## <a name="completing-questionnaires"></a>Wypełnianie kwestionariusza
Po zaprojektowaniu i rozesłaniu kwestionariusza, kwestionariusz może zostać wypełniony przez wybranych respondentów. Kwestionariusze można wypełniać w dwóch lokalizacjach:

-   W okienku nawigacji kliknij kolejno opcje **Kwestionariusze** &gt; **Dystrybuuj** &gt; **Wypełnianie kwestionariusza**.
-   W obszarze Samoobsługa pracownika etatowego kliknij **Kwestionariusze do wypełnienia**.

Kwestionariusze można udostępnić wszystkich osobom w sieci, określonym użytkownikom lub grupom użytkowników.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Projektowanie kwestionariuszy](design-questionnaires.md)

[Używanie kwestionariuszy](questionnaires.md)

[Wyświetlanie i ocena wyników kwestionariuszy](evaluate-questionnaire-results.md)


