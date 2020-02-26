---
title: Generowanie raportów do ustawy ACA (Affordable Care Act)
description: Jest dostępna funkcjonalność wspierająca pracodawców, którzy muszą monitorować informacje zgłaszane w deklaracjach 1095-B i 1095-C dotyczących sekcji Employer Mandate (Obowiązki pracodawcy) amerykańskiej ustawy o powszechnym dostępie do opieki zdrowotnej (ACA). Należy zauważyć, że ta funkcjonalność jest włączona tylko dla firm w Stanach Zjednoczonych.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 47532861203fedbffc49aa92d25fc99de9d25376
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010221"
---
# <a name="generate-affordable-care-act-aca-reports"></a>Generowanie raportów do ustawy ACA (Affordable Care Act)

Jest dostępna funkcjonalność wspierająca pracodawców, którzy muszą monitorować informacje zgłaszane w deklaracjach 1095-B i 1095-C dotyczących sekcji **Employer Mandate** (Obowiązki pracodawcy) amerykańskiej ustawy o powszechnym dostępie do opieki zdrowotnej (ACA). Należy zauważyć, że ta funkcjonalność jest włączona tylko dla firm w Stanach Zjednoczonych.

## <a name="getting-started"></a>Rozpoczęcie pracy
Rozpoczynając śledzenie informacji przeznaczonych do zgłaszania w deklaracjach 1095-B i 1095-C, należy najpierw utworzyć jedną lub więcej grup objętych świadczeniem ACA. Te grupy objęte świadczeniem ACA będą używane w celu wskazania oferty zakresu świadczeń dostarczonej pracownikowi, udziału pracownika w płaceniu najniższej miesięcznej składki (jeśli koszt przekracza federalną granicę ubóstwa) oraz zasad „bezpiecznej przystani” (programu Safe Harbor) stosowanych przez pracodawcę (jeśli dotyczy). Za pomocą grup ACA można zarządzać informacjami dla tych pól bez konieczności otwierania rekordów wszystkich pracowników mających takie same warunki. Ponadto grupy objęte świadczeniem ACA można łatwo przypisać do jednego lub wielu pracowników przy użyciu funkcji przypisywania grupowego dostępnej na stronie.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Prowadzenie wielu wersji grupy objętej świadczeniem
W systemie można zarządzać wieloma wersjami każdej grupy objętej świadczeniem, co pozwala wprowadzać zmiany utrzymujące aktualność informacji w grupie bez konieczności tworzenia nowej grupy ani przypisywania do niej pracowników, gdy coś się zmieni w organizacji lub w oferowanych świadczeniach. 

Po utworzeniu potrzebnych grup objętych świadczeniem ACA można je zbiorczo przypisać do pracowników przy użyciu funkcji **Przypisanie grupowe** dostępnej na stronie albo przejść indywidualnie do każdego pracownika i wskazać, czy informacje ACA muszą być śledzone i zgłaszane dla tego pracownika, jak również przypisać tego pracownika do grupy objętej świadczeniem ACA.

Jeśli informacje dotyczące objęcia świadczeniem ACA nie muszą być śledzone ani zgłaszane dla pracownika, na przykład gdy osoba ta pracuje na niepełny etat, to w polu **Zgłaszaj objęcie świadczeniem** można ustawić wartość Nie. Chociaż każdy pracownik, dla którego muszą być śledzone informacje ACA, musi być przypisany do grupy objętej świadczeniem ACA, nadal można modyfikować opcje **Oferta świadczenia**, **Udział pracownika etatowego w koszcie** i **"Program Safe Harbor"** dla dowolnych miesięcy, które mogą wymagać wartości innych niż wprowadzone w grupie objętej świadczeniem ACA.

Aby wprowadzić wyjątki od którychkolwiek wartości grupy objętej świadczeniem ACA, kliknij łącze Świadczenie ACA znajdujące się na stronie Szczegóły pracownika, pod sekcją Informacje dodatkowe: na karcie Zatrudnienie.

## <a name="reporting-health-care-coverage"></a>Zgłaszanie objęcia świadczeniem zdrowotnym
Można śledzić nie tylko, jaki zakres ubezpieczenia zdrowotnego zaoferowano pracownikowi pełnoetatowemu, ale jeśli pracodawca oferuje dodatkowe finansowane przez firmę ubezpieczenie zdrowotne, z którego korzysta pracownik (niezależnie od tego, czy jest zatrudniony w pełnym czy niepełnym wymiarze godzin), w deklaracji 1095-C trzeba podać dodatkowe informacje. Każdy pracownik (w tym osoby na jego utrzymaniu) objęty systemem świadczeń finansowanym przez pracodawcę musi być wykazany w raporcie za miesiące, w których był objęty świadczeniem. 

Aby wskazać, że dany plan świadczeń musi być zgłaszany, można zaznaczyć pole wyboru **Podlega zgłoszeniu na mocy ACA**.

Ponadto jeśli pracownicy wybrali objęcie świadczeniem jakichkolwiek osób pozostających na ich utrzymaniu, na stronie Obsługa świadczeń można podać daty objęcia osób zależnych dla każdego pracownika. Aby wskazać, że osoba na utrzymaniu jest objęta świadczeniem, kliknij przycisk Edytuj w okienku akcji na skróconej karcie Osoby zależne.

Na stronie **Menedżer dat świadczenia dla osoby będącej na utrzymaniu** można podać daty objęcia osoby na utrzymaniu świadczeniem. Wprowadzenie dat na tej stronie spowoduje automatyczne zaznaczenie pola wyboru **Pokryte** na stronie **Obsługa świadczeń**.

## <a name="generate-1095b-and-1095c-forms"></a>Generowanie deklaracji 1095B i 1095C
Formularze 109-B i 1095-C można również wygenerować z poziomu programu i rozesłać je odnośnym pracownikom. Z systemu można też elektronicznie wygenerować deklarację 1095-C i towarzyszące jej pliki 1094-C przekazywane do urzędu skarbowego.  

Podczas generowania formularza 1095-C należy wprowadzić odpowiedni rok podatkowy i wskazać, czy numer ubezpieczenia społecznego powinien być zakryty. W wypadku drukowania formularzy 1095-C dla więcej niż 500 pracowników otrzymasz więcej niż jeden plik PDF. Zaleca się zwiększenie **maksymalnego rozmiaru pliku** w oknie **Parametry zarządzania dokumentami** na 150 MB.

## <a name="viewing-information"></a>Wyświetlanie informacji
Na stronie **Świadczenie ACA dla pracownika** można zobaczyć, których pracowników przypisano do poszczególnych grup objętych świadczeniem, których pracowników nie trzeba uwzględniać w raporcie i którzy pracownicy są nieprzypisani.

Jeśli którakolwiek domyślna wartość grupy objętej świadczeniem ACA zostanie zastąpiona, obok niej będzie widoczna gwiazdka. Jeśli wartości dla wszystkich dwunastu miesięcy są takie same i nie zostały zastąpione, wartość zostanie wydrukowana w kolumnie **Wszystkie 12 miesięcy**.

Można również użyć okna zapytania, aby sprawdzić, którym pracownikom ustawiono flagę niepodlegania zgłoszeniu na mocy ACA, co oznacza, że nie trzeba śledzić, czy zaoferowano im objęcie świadczeniem, i nie trzeba im generować deklaracji 1095-C na koniec roku. Zaznaczając opcję **Nie podlega zgłoszeniu na mocy ACA** w polu **Filtruj według**, można wygenerować listę wszystkich pracowników, którym ustawioną flagę niegenerowania formularza 1095-C.

Oprócz przeglądania listy pracowników niepodlegających zgłaszaniu według ustawy ACA można również wyświetlić pracowników, którzy nie są przypisani (mają puste pole **Objęcie zgłaszaniem na mocy**) lub zostali przypisani do grupy objętej świadczeniem ACA, która wygasła dla roku wybranego w polu **Rok**.

Można wyeksportować wygenerowaną listę pracowników, używając dowolnej opcji filtrowania do programu Excel.

Jeśli musisz zgłosić osoby objęte świadczeniem, ponieważ jako pracodawca oferujesz dodatkowe świadczenia finansowane przez siebie, możesz także wyświetlić wszystkie osoby na utrzymaniu objęte takimi planami świadczeń oznaczone jako **Podlega zgłoszeniu na mocy ACA**, klikając akcję Wyświetl świadczenie dla osoby na utrzymaniu na pasku w okienku akcji.

**Uwaga:** W oknie zapytania będą wyświetlane tylko świadczenia, których plan został oznaczony jako **Podlega zgłoszeniu na mocy ACA**.
