---
title: "Formalizowanie procesów biznesowych"
description: "Funkcja procesów biznesowych pozwala utworzyć szablon procesu biznesowego dla procesów, które muszą być wykonywane w organizacji."
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
ms.sourcegitcommit: 812db9f1d319e4d16f83700a7153a0a3b318963e
ms.openlocfilehash: 48f80eac5009e1a241d501b0c4a3a70b78f5d709
ms.contentlocale: pl-pl
ms.lasthandoff: 03/23/2018

---
# <a name="formalize-business-processes"></a>Formalizowanie procesów biznesowych
Funkcja procesów biznesowych pozwala utworzyć szablon procesu biznesowego dla procesów, które muszą być wykonywane w organizacji. Na przykład firma może corocznie wykonywać audyt kadrowy. Można utworzyć szablon śledzący wszystkie zadania zawarte w audycie, aby mieć pewność, że wszystkie zadania są wykonywane każdorazowo podczas wykonywania procesu, a w razie potrzeby również zapewnić, że zadania są wykonywane w poprawnej kolejności. Szablony mogą być wykorzystywane bez zmian w procesach cyklicznych lub kopiowane w celu użycia jako punkty wyjściowe do tworzenia nowych szablonów.

Po utworzeniu szablonu można uruchomić i śledzić proces w obszarze roboczym Proces biznesowy.  Po rozpoczęciu procesu biznesowego zadania zostaną przypisane do odpowiednich osób i będą zawierały termin wykonania. Poniżej szczegółowo omówimy te składniki.

## <a name="business-process-template"></a>Szablon procesu biznesowego
Szablon procesu biznesowego zawiera listę grup zadań, które składają się na proces biznesowy. Menedżerowie i asystenci ds. kadr mogą tworzyć procesy biznesowe domyślnie.  Można to jednak zmienić w konfiguracji zabezpieczeń poprzez edycję obowiązku Obsługa ogólnych procesów biznesowych.

Dla każdego procesu można zdefiniować właściciela procesu.  Właściciel procesu będzie miał wgląd we wszystkie zadania w procesie oraz będzie mógł zmieniać ich przypisania i terminy wykonania.  Na przykład dyrektor działu kadr może utworzyć szablon procesu biznesowego dla przeglądu świadczeń.  Menedżer ds. wynagrodzeń i świadczeń może zostać ustawiony jako właściciel procesu, dzięki czemu będzie miał wgląd w zadania, które trzeba wykonać w ramach przeglądu.  Właściciel procesu nie może tworzyć ani usuwać aktywnych procesów biznesowych oraz szablonów procesów biznesowych.

## <a name="task"></a>Zadanie
Proces biznesowy często składa się z wielu zadań. Niektóre zadania, takie jak przegląd oferty kursów wewnętrznych, można wykonywać wewnątrz programu Dynamics 365 for Talent[?]. W takim przypadku Łącze do zadania należy wybrać opcję Element menu. Inne zadania mogą obejmować przegląd lub wypełnianie formularzy w witrynie sieci Web. Jeśli w polu Łącze do zadania zaznaczysz pozycję Adres URL, będzie można wprowadzić adres sieci web. W tym polu można wprowadzać adresy URL witryn wewnętrznych i zewnętrznych. Można również tworzyć zadania dla działań wykonywanych ręcznie, takich jak przeglądanie dostępności wszystkich struktur. W takim przypadku łącze do zadania nie jest wymagane. Ta elastyczność pozwala śledzić wiele rodzajów zadań w kompleksowym procesie.

Zadania można przypisywać do konkretnych pracowników lub do stanowisk. Na przykład menedżer ds. wynagrodzeń i świadczeń zawsze będzie osobą, która dokonuje przeglądu składek ubezpieczeniowych.   Podczas tworzenia tego zadania w polu Typ przypisania wybierz wartość Stanowisko, a następnie na liście Stanowisko zaznacz pozycję Menedżer ds. wynagrodzeń i świadczeń. Podczas uruchamiania procesu zadanie zostanie przypisane do pracownika, który zajmuje stanowisko menedżera ds. wynagrodzeń i świadczeń. Można także przypisać zadanie do konkretnego pracownika, w polu Typ przypisania wybierając wartość Pracownik, a następnie wybierając odpowiednią osobę.

Terminy wykonania zadań zależą od daty docelowej wprowadzonej na początku procesu. Niektóre zadania muszą zostać wykonane przed datą docelową, a niektóre można wykonać po tym dniu.  Podczas definiowania zadania w polu Przesunięcie daty wymagalności od daty docelowej wprowadzisz termin wykonania względny wobec daty docelowej. Na przykład załóżmy, że menedżer ds. wynagrodzeń i świadczeń musi wykonać przegląd składek ubezpieczeniowych 10 dni przed zakończeniem audytu kadrowego. Utworzone zadanie będzie miało termin wykonania -10 względem daty docelowej. W związku z tym jeśli proces zacznie się 13 maja, zadanie należy ukończyć do 3 maja. Uwaga: Terminy wykonania można również korygować po rozpoczęciu procesu.

Złożone zadania mogą wymagać większej liczby kroków albo podania dodatkowych informacji przez osobę wykonującą zadanie. Do zadania można dodać instrukcje i w razie potrzeby różnorodnie sformatować ich tekst. Instrukcje mogą przekazywać dodatkowe informacje dotyczące sposobu wykonania zadania dla osoby, której przypisano wykonanie zdania.

Uruchamianie procesu Proces można uruchomić w szablonie procesu biznesowego, wybierając opcję Rozpocznij proces.  Po uruchomieniu procesu zadania zostaną utworzone dla wybranych pracowników i/lub stanowisk określonych w zadaniach, które uwzględniono w szablonie procesu biznesowego. Do każdego zadania zostanie również przypisany termin poprzez dodanie lub odjęcie dni przesunięcia względem daty docelowej (patrz informacje dotyczące dni przesunięcia w sekcji Zadanie). Aktywne procesy biznesowe można wyświetlać w obszarze roboczym Procesy biznesowe. 

## <a name="employee-self-service"></a>Samoobsługa pracownika
Gdy zadanie zostanie przypisane do pracownika, zadania przydzielone tej osobie można wyświetlić na stronie Samoobsługa pracownika etatowego. Pracownicy mający przypisane zadanie procesu biznesowego mogą ze swojej strony Samoobsługa pracownika etatowego wyświetlić zadanie, jego opis, instrukcje wykonania oraz imię i nazwisko osoby kontaktowej, a także otworzyć skojarzoną stronę programu Dynamics365 lub stronę sieci web. Zadania mogą być oznaczone jako w roku, anulowane lub ukończone.

## <a name="business-process-workspace"></a>Obszar roboczy Proces biznesowy
Pracownicy działu kadr mogą wyświetlać aktywne procesy biznesowe w obszarze roboczym Proces biznesowy. Ten obszar roboczy zawiera listę wszystkich aktywnych procesów oraz skojarzonych z nimi zadań. Tę kompleksową listę zadań można filtrować według terminu wykonania. Strona zawiera także listę zadań zaległych oraz zadań przypisanych konkretnie pracownikowi działu kadr. Pracownicy działu kadr mogą także aktualizować stan wszystkich zadań, a w razie potrzeby zmieniać przypisanie zadań w celu sprawniejszej realizacji całego procesu biznesowego.

## <a name="my-business-processes-workspace"></a>Obszar roboczy Moje procesy biznesowe
W obszarze roboczym Mój proces biznesowy właściciele procesów mogą wyświetlać przypisane im aktywne procesy biznesowe. Ten obszar roboczy zawiera listę wszystkich aktywnych procesów i skojarzonych z nimi zadań, których właścicielem jest użytkownik.  Tę kompleksową listę zadań można filtrować według terminu wykonania. Strona zawiera również listę zadań przypisanych konkretnie właścicielowi procesu. Właściciel procesu może również aktualizować stan wszystkich zadań, a także zmieniać przypisania zadań.

## <a name="navigating-business-processes"></a>Nawigowanie po procesach biznesowych
1.   Aby dodać szablon procesu biznesowego, wybierz kolejno opcje Procesy biznesowe > Łącza > Administrowanie procesami biznesowymi.
 - a.   Przycisk Nowy spowoduje utworzenie nowego szablonu.
 - b.   Przycisk Kopiuj z szablonu spowoduje skopiowanie wybranego szablonu do nowego szablonu.
 - c.   Przycisk Rozpocznij proces spowoduje uruchomienie wybranego procesu biznesowego, przypisanie zadań i obliczenie terminów wykonania.  
2.  Aby wyświetlić aktywne procesy i skojarzone z nimi zadania, przejdź do obszaru roboczego Procesy biznesowe.

