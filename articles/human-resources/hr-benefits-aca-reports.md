---
title: Generowanie raportów do amerykańskiej ustawy o powszechnym dostępie do opieki zdrowotnej (Affordable Care Act, ACA)
description: Sprawozdawczość ACA (ACA) generuje formularze 1095-B i 1095-C na podstawie części z **Upoważnieniem pracodawcy** w ustawieACA.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 56ff879603a31956db877b45aec11b15371b69f5
ms.sourcegitcommit: 5c1b5ef40ce7359b3f1955535a250718d863badb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2021
ms.locfileid: "5142163"
---
# <a name="generate-aca-reports"></a>Generowanie raportów ACA

Sprawozdawczość ACA (ACA) generuje formularze 1095-B i 1095-C na podstawie części z **Upoważnieniem pracodawcy** w ustawieACA.

> [!NOTE]
> Raportowanie ACA jest włączone tylko dla firm w Stanach Zjednoczonych.

## <a name="getting-started"></a>Rozpoczęcie pracy

Aby śledzić informacje dla formularzy 1095-B i 1095-C, musisz najpierw utworzyć jedną lub więcej grup objętych opieką w przystępnej cenie. Grupy ubezpieczeniowe w przystępnej cenie wskazują:

- Oferta świadczenia dla pracownika
- Udział pracownika w najniższej miesięcznej składce, jeśli koszt przekracza federalną granicę ubóstwa
- Bezpieczna Przystań, z którego korzysta pracodawca, jeśli ma to zastosowanie

Grupy ubezpieczenia Affordable Care pozwalają na zarządzanie informacjami w tych polach bez zmiany każdego rekordu pracownika, gdy warunki są takie same. Możesz łatwo przypisać grupy ubezpieczeniowe Affordable Care jednemu lub większej liczbie pracowników, korzystając z opcji **Przydzielania masowego** na stronie.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Prowadzenie wielu wersji grupy objętej świadczeniem

Możesz utrzymywać wiele wersji dowolnej grupy pokrycia. Ta funkcja umożliwia wprowadzać zmiany bez konieczności tworzenia nowej grupy i ponownego przypisania do niej pracowników. 

Po utworzeniu grup zapotrzebowania ACA można je grupnie przypisywać do pracowników za pomocą opcji **Grupowe przypisywanie**. Można również indywidualnie określić, czy mają być śledzone i zgłaszane informacje ACA, oraz przypisać pracownika do grupy świadczenia ACA.

Nie musisz śledzić niektórych informacji o zasięgu ACA, na przykład dla pracowników zatrudnionych w niepełnym wymiarze godzin. W takim przypadku w polu **Zgłaszaj objęcie świadczeniem** należy ustawić wartość **Nie**. Chociaż musisz przypisać każdego pracownika z możliwymi do śledzenia informacjami ACA do grupy objętej ubezpieczeniem Affordable Care, nadal możesz zmienić następujące opcje dla miesięcy z różnymi wartościami:

- **Oferta świadczenia**
- **Udział pracownika w koszcie**
- **Bezpieczna przystań**

Aby wprowadzić wyjątki od którychkolwiek wartości grupy objętej świadczeniem Affordable Care, kliknij łącze **Świadczenie ACA** znajdujące się na stronie **Szczegóły pracownika**, pod sekcją **Informacje dodatkowe**: na **karcie Zatrudnienie**.

## <a name="reporting-health-care-coverage"></a>Zgłaszanie objęcia świadczeniem zdrowotnym

Można śledzić nie tylko, jaki zakres ubezpieczenia zdrowotnego zaoferowano pracownikom pełnoetatowym, ale jeśli pracodawca oferuje dodatkowe finansowane przez firmę ubezpieczenie zdrowotne, z którego korzysta pracownik (niezależnie od tego, czy jest zatrudniony w pełnym czy niepełnym wymiarze godzin), w deklaracji 1095-C trzeba podać dodatkowe informacje. Każdy pracownik (w tym osoby na jego utrzymaniu) objęty systemem świadczeń finansowanym przez pracodawcę musi być wykazany w raporcie za miesiące, w których był objęty świadczeniem. 

Aby wskazać, że dany plan świadczeń musi być zgłaszany, można zaznaczyć pole wyboru **Podlega zgłoszeniu na mocy ACA**.

Ponadto jeśli pracownicy wybrali objęcie świadczeniem jakichkolwiek osób pozostających na ich utrzymaniu, na stronie **Obsługa świadczeń** można podać daty objęcia osób zależnych dla każdego pracownika. Aby wskazać, że osoba na utrzymaniu jest objęta świadczeniem, kliknij przycisk **Edytuj** w okienku akcji na skróconej karcie **Osoby zależne**.

Na stronie **Menedżer dat świadczenia dla osoby będącej na utrzymaniu** można podać daty objęcia osoby na utrzymaniu świadczeniem. Wprowadzenie dat na tej stronie spowoduje automatyczne zaznaczenie pola wyboru **Pokryte** na stronie **Obsługa świadczeń**.

## <a name="generate-1095-b-and-1095-c-forms"></a>Generowanie formularzy 1095-B i 1095-C

Formularze 1095-B i 1095-C można również wygenerować z poziomu programu i rozesłać je odnośnym pracownikom. System może także elektronicznie generować formularze 1095-C oraz pliki przekazu 1094-C IRS.  

Podczas generowania formularza 1095-C należy wprowadzić odpowiedni rok podatkowy i wskazać, czy numer ubezpieczenia społecznego powinien być zakryty. W wypadku drukowania formularzy 1095-C dla więcej niż 500 pracowników otrzymasz więcej niż jeden plik PDF. Zaleca się zwiększenie **maksymalnego rozmiaru pliku** w oknie **Parametry zarządzania dokumentami** na 150 MB.

## <a name="viewing-information"></a>Wyświetlanie informacji

Na stronie **Świadczenie ACA dla pracownika** można zobaczyć, których pracowników przypisano do poszczególnych grup objętych świadczeniem, których pracowników nie trzeba uwzględniać w raporcie i którzy pracownicy są nieprzypisani.

Jeśli którakolwiek domyślna wartość grupy objętej świadczeniem ACA zostanie zastąpiona, obok niej będzie widoczna gwiazdka. Jeśli wartości dla wszystkich dwunastu miesięcy są takie same i nie zostały zastąpione, wartość zostanie wydrukowana w kolumnie **Wszystkie 12 miesięcy**.

Ponadto za pomocą okna informacji można zrozumieć, którzy pracownicy zostały oflagowane jako nie mogą być raportowane na podstawie ACA. Nie trzeba śledzić, czy zaoferował im pokrycie i nie trzeba na koniec roku wystawiać im 1095-C. Wybierz opcję **Nie do zgłoszenia do ACA** w polu **Filtruj według**, aby wygenerować listę wszystkich pracowników, którzy nie otrzymają raportu1095-C.

Można również wyświetlić pracowników, którzy nie są przypisani (mają puste pole **Objęcie zgłaszaniem na mocy**) lub zostali przypisani do grupy objętej świadczeniem ACA, która wygasła dla roku wybranego w polu **Rok**.

Można wyeksportować wygenerowaną listę pracowników, używając dowolnej opcji filtrowania do programu Excel.

Jeśli chcesz zgłosić osoby objęte ubezpieczeniem, ponieważ zapewniasz ubezpieczenie samodzielnie, możesz wyświetlić wszystkie osoby na utrzymaniu objęte planem świadczeń oznaczonych jako **Objęte zgłoszeniem do ACA**. Na okienku akcji wybierz **Wyświetl świadczenia osób na utrzymaniu**.

> [!NOTE]
> W oknie informacji można wyświetlać tylko plany świadczeń oznaczone jako **Objęte zgłoszeniem do ACA**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]