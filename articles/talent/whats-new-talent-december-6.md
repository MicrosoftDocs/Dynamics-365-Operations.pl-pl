---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (6 grudnia 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e46000414436b5a2fa211428dcd10131b9d588c1
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897702"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-december-6-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (6 grudnia 2018 r.)

**Kompilacja 8.1.2071**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.


## <a name="platform-update-22-for-finance-and-operations"></a>Aktualizacja Platform update 22 dla Finance and Operations

### <a name="export-up-to-1-million-rows-to-excel"></a>Eksportowanie do 1 miliona wierszy do programu Excel

Funkcję eksportowania do programu Excel można skonfigurować tak aby użytkownicy mogli eksportować do 1 miliona wierszy z siatki w rozwiązaniu Talent; jest to duży wzrost w porównaniu z wcześniejszym limitem 10 000 wierszy. 

### <a name="restyled-personalization-toolbar"></a>Zmiana stylu paska narzędzie personalizacji

Pasek narzędzi personalizacji został zmieniony w aktualizacji Platform update 22 dla Finance and Operations, pomagając w dostosowaniu środowiska Talent do potrzeb użytkowników. Wprowadzono następujące zmiany: 

-  Nazwa każdego narzędzia personalizacji jest teraz wyświetlana wraz z ikoną, która pomaga użytkownikom szybko rozpoznawać narzędzie, którego chcą użyć.
-  Wyświetlany jest również opis sposobu używania bieżącego narzędzia, który pomaga w zrozumieniu sposobu wprowadzania personalizacji.  
-  Cały pasek narzędzi personalizacji można przesuwać po ekranie w określonym regionie skrajnie z lewej strony paska narzędzi. Dzięki temu użytkownicy mogą zapisywać indywidualne elementy, które zostały wcześniej zasłonięty przez pasek narzędzi.   

### <a name="optimized-is-one-of-filtering-experience"></a>Optymalizacja funkcji filtrowania „jest jednym z”

Operator filtrowania „jest jednym z” jest dostępny dla większości pól podczas korzystania z Okienka filtru i list rozwijanych nagłówka. Ten operator pozwala użytkownikowi filtrować pola na podstawie wielu wartości. Nowe i ulepszone funkcjonowanie operatora „jest jednym z” jest dostępne w aktualizacji Platform update 22 dla Finance and Operations. Aby dowiedzieć się więcej, zobacz [Optymalizowanie funkcji filtrowania „jest jednym z”](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Wklejanie list z programu Excell do pól filtra z operatorem "jest jednym z"

W przypadku niektórych zadań użytkownicy mogą mieć listę wartości w programie, którą chcą użyć do filtrowania danych w Talent. Na przykład użytkownik w dziale HR może mieć określony na podstawie raportu zbiór pracowników, wymagający dalszego badania w systemie, i dla takiego użytkownika idealnym rozwiązaniem byłaby możliwość skopiowania listy bezpośrednio z programu Excel do pola filtra w Talent.

Począwszy od aktualizacji Platform update 22 dla Finance and Operations, operator „jest jednym z” w okienku filtru i filtrowaniu kolumn siatki rozpoznaje teraz wartości skopiowane z programu Excel, dzięki czemu można je wkleić bezpośrednio do pola filtru. Obejmuje to zbiór wartości skopiowanych z różnych wierszy i kolumn w programie Excel. Aby dowiedzieć się więcej o tej funkcji, zobacz [Wklejanie list z programu Excel do pól filtru z operatorem „jest jedną z”](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>Wersja próbna

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Konfigurowanie integracji listy płac w Wielkiej Brytanii między rozwiązaniami Talent i Dayforce

Integracja między rozwiązaniami Talent i Ceridian Dayforce jest dostępna w wersji próbnej w Wielkiej Brytanii. Aby uzyskać więcej informacji, zobacz poniższy temat [Konfigurowanie integracji list płac między rozwiązaniami Talent i Dayforce](https://docs.microsoft.com/dynamics365/unified-operations/talent/configure-payroll-integration).

## <a name="coming-soon"></a>Wkrótce

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Urlopy i nieobecności: przyszłe i urlopy i prognozowane saldo urlopów

Zmiany dotyczą opcji zezwalania pracownikom na przewidywanie czasu wolnego i przyszłych wniosków o czas wolny bez wpływu na aktualne saldo czasu wolnego, dlatego zmienia się również sposób wyświetlania czasu wolnego. 

Dostępne saldo aktualnie wyświetlana jest ilością czasu wolnego od pracy dostępną na żądania w tym naliczenia do dnia dzisiejszego oraz wszelkie zatwierdzone wnioski urlopowe do końca czasu. 

Po zwolnieniu zdolność do prognozy wyświetlane saldo zmienia się na bieżące saldo czasu wolnego wraz z naliczeniami i wnioskami do dnia dzisiejszego. Pracownicy i menedżerowie zobaczą te zaktualizowane salda w panelach samoobsługowych dla pracowników i menedżerów na karcie **Czas wolny** w oknie **Sala czasu wolnego**. Menedżerów HR będzie widział te zaktualizowane salda w przestrzeni roboczej **Osoby** i w oknie pracownika **Przypisane plany urlopów**.

## <a name="other-changes"></a>Inne zmiany 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>Kod zakończenia zatrudnienia nie jest wyprowadzany w rekordzie przypisania stanowiska pracownika

Zmiana została zaimplementowana, która wypełnia kod przyczyny w rekordzie przypisania stanowiska podczas procesu zakończenia zatrudnienia.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>Sprawdzanie poprawności numeru pracownika będącego w użyciu wymaga dodatkowych informacji

Dodatkowe informacje są wyświetlane podczas używania sekwencji numerów, aby lepiej zrozumieć problemy, gdy nie można wygenerować nowego numeru.
 
### <a name="attachments-buttons-not-available-for-workers"></a>Przyciski załączników niedostępne dla pracowników

Wprowadzono zmiany mające na celu poprawienie załączników. Podczas dodawania nowego załącznika do pracownika, przyciski **Nowy** i **Edytuj** są teraz dostępne, gdy pola informacji są otwarte w oknie pracownika. 

## <a name="known-issues"></a>Znane problemy

### <a name="mapping-errors-in-the-integration-with-finance"></a>Błędy mapowania w integracji z Finance

Zidentyfikowano następujące problemy w bieżącym szablonie dotyczącego integracji rozwiązania Talent z rozwiązaniem Finance. Nowy szablon zostanie wkrótce opublikowany i będzie stosowany do wszystkich nowych projektów integracji, które zostały utworzone. Dla istniejących projektów integracji mapowania zadań mogą być zaktualizowane. Zaktualizowane mapowania można znaleźć w poniższej tabeli. 

>[!NOTE]
> Zadanie Stanowiska do Przypisania pracy nadrzędnej do stanowisk nie integruje danych. Występuje problem, który jest aktualnie badany. Obecnie nie ma rozwiązania problemu mapowania. 

Zadanie Działy do Jednostka operacyjna musi mieć zaktualizowane następujące mapowania.

| Pole istniejącego źródła          | Pole nowego źródła |
| -------------------------------|------------------|
| cdm_description (Opis)  | cdm_name (nazwa)  |

Dodatkowe mapowanie również musi zostać dodane. Wybierz ostatnie pole **Brak**, aby dodać następujące mapowanie.

| Pole źródłowe                   | Pole docelowe    |
| -------------------------------|----------------------|
| cdm_description (Opis)  | NAMEALIAS (NAMEALIAS)|

Zaktualizowane mapowanie powinno wyglądać tak.

![Zadanie Działy na jednostki operacyjne](./media/DepartmentMapping.png)


Zadanie Prace na szczegóły pracy musi mieć zaktualizowane następujące mapowania.

| Pole istniejącego źródła          | Pole nowego źródła                   |
| -------------------------------|------------------------------------|
| cdm_name (nazwa)                | cdm_description (Opis)      |
| cdm_name (opis)         | cdm_jobdescription(opis zadania)|


Zaktualizowane mapowanie powinno wyglądać tak.

![Zadanie Praca na szczegóły pracy](./media/JobMapping.png)

Zadanie Pracownicy na pracownika musi mieć zaktualizowane następujące mapowania.

| Pole istniejącego źródła                 | Pole nowego źródła                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (adres e-mail 1)   | cdm_primaryemailaddress (główny adres e-mail) |
| cdm_telephone1 (telefon 1)          | cdm_primarytelephone (główny numer telefonu)       |

Przekształcenie pola płci również musi zostać zaktualizowane. Wybierz typ mapy **fn** (funkcja) dla płci i zaktualizuj następujące mapowania wartości.

| Wartość Common Data Service | Wartość Finance and Operations | | ------------|------------------ -----------| | 75440000    | Mężczyzna                         | | 75440001    | Kobieta                       | | 75440002    | Brak                         | | 75440003    | Nie określono                  |

Zaktualizowane mapowanie powinno wyglądać tak.

![Zadanie Pracownicy na pracownika](./media/WorkerMapping.png)

![Przekształcenie pola płci](./media/WorkerTransform.png)

