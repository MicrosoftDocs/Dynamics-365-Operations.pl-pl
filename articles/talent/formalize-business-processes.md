---
title: "Formalizowanie procesów biznesowych"
description: "W tym temacie wyjaśniono, jak za pomocą funkcji Proces biznesowy można utworzyć szablon procesu biznesowego dla procesów, które muszą być wykonywane w organizacji."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ee4035f3156a91faecdecba45289dbb1ca6e947a
ms.openlocfilehash: fd538677d897c1e7d3103cd714c688373aab8d29
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="formalize-business-processes"></a>Formalizowanie procesów biznesowych

[!include[banner](includes/banner.md)]

Funkcja Proces biznesowy pozwala utworzyć szablon procesu biznesowego dla procesów biznesowych, które muszą być wykonywane w organizacji. Na przykład firma co rok przeprowadza audyt zasobów ludzkich (HR). W takim wypadku można utworzyć szablon, który śledzi wszystkie zadania wchodzące w skład procesu inspekcji. Ten szablon pomoże zagwarantować, że wszystkie zadania są wykonywane podczas każdej sesji audytu. Ponadto jeśli zadania muszą zostać wykonane w określonej kolejności, szablon może pomóc tego dopilnować.

Szablony mogą być wykorzystywane w procesach cyklicznych. Można je również kopiować i używać jako punktu wyjścia do tworzenia nowych szablonów.

Po utworzeniu szablonu procesu biznesowego można uruchomić i śledzić proces biznesowy w obszarze roboczym **Proces biznesowy**. Po rozpoczęciu procesu biznesowego zadania są przypisywane do odpowiednich osób i zawierają termin wykonania.

## <a name="business-process-templates"></a>Szablony procesów biznesowych
Szablon procesu biznesowego zawiera listę grup zadań, które składają się na proces biznesowy. Domyślnie procesy biznesowe mogą tworzyć menedżerowie i asystenci ds. kadr. Można jednak zmienić role, które mogą tworzyć procesy biznesowe, modyfikując obowiązek **Obsługa ogólnych procesów biznesowych** w konfiguracji zabezpieczeń.

Dla każdego procesu biznesowego można zdefiniować właściciela procesu. Właściciel procesu ma wgląd we wszystkie zadania w procesie oraz może zmieniać ich przypisania i terminy wykonania. Na przykład dyrektor działu kadr tworzy szablon procesu biznesowego w celu przeglądu świadczeń i wyznacza menedżera ds. wynagrodzeń i świadczeń jako właściciela procesu. Wtedy menedżer ds. wynagrodzeń i świadczeń będzie miał wgląd w zadania, które trzeba wykonywać w ramach przeglądu.

Właściciel procesu nie może tworzyć nowych procesów biznesowych ani szablonów procesów biznesowych, a także nie może usuwać aktywnych procesów biznesowych i szablonów procesów biznesowych.

## <a name="tasks"></a>Zadania
Proces biznesowy często składa się z wielu zadań. Niektóre zadania, takie jak przegląd oferty kursów wewnętrznych, można wykonywać wewnątrz programu Microsoft Dynamics 365 for Talent[?]. W takim przypadku należy zaznaczyć odpowiednią opcję w polu **Łącze do zadania**. Inne zadania mogą obejmować przegląd lub wypełnianie stron w witrynie internetowej. W takim przypadku należy zaznaczyć opcję **Adres URL** w polu **Łącze zadania**, co pozwoli wprowadzić adres internetowy. Można wprowadzać adresy URL witryn wewnętrznych i zewnętrznych. Można również tworzyć zadania dla działań wykonywanych ręcznie, takich jak przegląd dostępności wszystkich struktur. W takim przypadku łącze do zadania nie jest wymagane. Ta elastyczność pozwala śledzić wiele rodzajów zadań w kompleksowym procesie.

Zadania można przypisywać do konkretnych pracowników lub do stanowisk. Na przykład menedżer ds. wynagrodzeń i świadczeń zawsze będzie osobą, która dokonuje przeglądu składek ubezpieczeniowych. Dlatego podczas tworzenia tego zadania wybierz wartość **Stanowisko** w polu **Typ przypisania**, a następnie wartość **Menedżer ds. wynagrodzeń i świadczeń** na liście **Stanowisko**. Po uruchomieniu procesu biznesowego zadanie zostanie przypisane do pracownika, który zajmuje stanowisko **Menedżera ds. wynagrodzeń i świadczeń**. Aby przypisać zadanie do konkretnego pracownika, w polu **Typ przypisania** wybierz wartość **Pracownik**, a następnie wybierz odpowiednią osobę.

Terminy wykonania zadań zależą od daty docelowej wprowadzonej na początku procesu biznesowego. Niektóre zadania muszą zostać wykonane przed datą docelową, a inne można wykonać po tym dniu. Podczas definiowania zadania w polu **Przesunięcie daty wymagalności od daty docelowej** wprowadzisz termin wykonania względny wobec daty docelowej. Na przykład menedżer ds. wynagrodzeń i świadczeń musi wykonać przegląd składek ubezpieczeniowych 10 dni przed zakończeniem audytu kadrowego. W takim przypadku zadanie tworzone dla przeglądu ma w polu **Przesunięcie daty wymagalności od daty docelowej** wartość **-10**. W związku z tym jeśli proces biznesowy zacznie się 13 maja, zadanie należy ukończyć do 3 maja.

> [!NOTE]
> Terminy wykonania można również korygować po rozpoczęciu procesu biznesowego.

Złożone zadania mogą wymagać większej liczby kroków albo podania dodatkowych informacji przez osoby wykonujące zadania. W tych scenariuszach można dodać instrukcje do zadania. Instrukcje mogą przekazywać dodatkowe informacje o sposobie wykonania dla osoby, której przypisano wykonanie zdania. W instrukcjach można nawet dołączyć tekst sformatowany.

## <a name="starting-a-business-process"></a>Uruchamianie procesu biznesowego
W szablonie procesu biznesowego można uruchomić proces biznesowy, wybierając opcję **Rozpocznij proces**. Po uruchomieniu procesu zadania są tworzone dla wybranych pracowników lub stanowisk określonych w zadaniach, które uwzględniono w szablonie. Do każdego zadania zostanie również przypisany termin wykonania poprzez dodanie lub odjęcie liczby dni przesunięcia względem daty docelowej, jak wyjaśniono w sekcji „Zadania”. Aktywne procesy biznesowe można wyświetlać w obszarze roboczym **Procesy biznesowe**.

## <a name="employee-self-service"></a>Samoobsługa pracownika
Gdy zadanie zostanie przypisane do pracownika, pracownik może wyświetlać to zadanie oraz wszystkie inne przypisane mu zadania na stronie **Samoobsługa pracownika etatowego**. Dla każdego przypisanego mu zadania procesu biznesowego pracownik może zobaczyć nazwę i opis zadania, instrukcje wykonania oraz imię i nazwisko osoby kontaktowej. Ze strony **Samoobsługa pracownika etatowego** pracownik może również otworzyć skojarzoną stronę programu Microsoft Dynamics 365 lub skojarzoną stronę internetową oraz oznaczyć zadania jako będące w toku, anulowane lub zakończone.

## <a name="business-process-workspace"></a>Obszar roboczy Proces biznesowy
Pracownicy działu kadr mogą wyświetlać aktywne procesy biznesowe w obszarze roboczym **Proces biznesowy**. Ten obszar roboczy zawiera listę wszystkich aktywnych procesów oraz skojarzonych z nimi zadań. Tę kompleksową listę zadań można filtrować według terminu wykonania. Obszar roboczy zawiera także listę zadań zaległych oraz zadań przypisanych konkretnie pracownikowi działu kadr. Pracownik działu kadr może także aktualizować stan wszystkich zadań, a w razie potrzeby zmieniać przypisanie zadań w celu sprawniejszej realizacji całego procesu biznesowego.

## <a name="my-business-processes-workspace"></a>Obszar roboczy Moje procesy biznesowe
W obszarze roboczym **Mój proces biznesowy** właściciele procesów mogą wyświetlać przypisane im aktywne procesy biznesowe. Ten obszar roboczy zawiera listę wszystkich aktywnych procesów, których właścicielem jest użytkownik, i skojarzonych z nimi zadań. Tę kompleksową listę zadań można filtrować według terminu wykonania. Obszar roboczy zawiera także listę zadań przypisanych konkretnie właścicielowi procesu. Właściciel procesu może również aktualizować stan wszystkich zadań oraz zmieniać przypisania zadań.

## <a name="navigating-business-processes"></a>Nawigowanie po procesach biznesowych
Aby utworzyć lub skopiować szablon procesu biznesowego lub aby rozpocząć proces biznesowy, wybierz kolejno opcje Procesy biznesowe > Łącza > Administrowanie procesami biznesowymi. W oknie można wykonać następujące czynności:

- Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon procesu biznesowego.
- Naciśnij przycisk **Kopiuj z szablonu**, aby skopiować wybrany szablon do nowego szablonu.
- Naciśnij przycisk **Rozpocznij proces**, aby uruchomić wybrany proces biznesowy, przypisać zadania i obliczyć terminy wykonania.

Aby wyświetlić aktywne procesy i skojarzone z nimi zadania, otwórz obszar roboczy **Procesy biznesowe**.


