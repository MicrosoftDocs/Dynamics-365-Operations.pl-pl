---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (26 marca 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
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
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b23860a7eda0ec9d75cca04728b7fc11d01bf967
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812748"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-26-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (26 marca 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="enhancements-to-interview-scheduling"></a>Rozszerzenia do Planowania rozmów kwalifikacyjnych
Następujące ulepszenia są dostępne w planowaniu rozmów kwalifikacyjnych.

- Osoby rekrutujące lub menedżerowie zatrudniający mogą teraz ręcznie wywołać przypomnienie dla oosby przeprowadzającej rozmowę kwalifikacyjną o konieczności przesłania opinii. Można także konfigurować skojarzony szablon przypomnienia.
- Udostępniając podsumowanie rozmowy kwalifikacyjnej kandydatowi, osoba planująca rozmowę kwalifikacyjną może wybrać opcję ukrycia nazwisk osób przeprowadzających rozmowę, a także ukrycia wierszy w widoku podsumowania rozmowy kwalifikacyjnej.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

### <a name="embedded-images-in-activities"></a>Obrazy osadzone w działaniach
Teraz można osadzać obrazy bezpośrednio w działaniach. Oprócz możliwości kopiowania i wklejania obrazów z sieci web, możesz przesyłać obrazy z lokalnego systemu plików. Rozmiar działania nie może przekraczać 1 MB. Jeśli obraz jest zbyt duży, zmień rozmiar i spróbuj ponownie go przesłać.

[![Mapowanie](./media/embedimages.png)](./media/embedimages.png)

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
**Kompilacja 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Dostępna jest niestandardowa pomoc dotycząca pól dla wybranych pozycji w Common Data Service 

Poniższe jednostki Common Data Service obsługują teraz pola odbiorcy utworzone w Talent:

- Pracownik
- Pochodzenie etniczne
- Status kombatanta
- Kod języka
- Zadanie
- Typ zadania
- Funkcja stanowiska
- Pozycja
- Typ stanowiska
 
### <a name="employment-history-not-displayed-chronologically"></a>Historia zatrudnienia nie jest wyświetlane w porządku chronologicznym
W związku z tą zmianą strona historii zatrudnienia wyświetla teraz rekordy zatrudnienia chronologicznie, niezależnie od firmy. Można też korzystać z opcjo sortowania, aby sortować według firmy.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>Plany stałych wynagrodzeń nie są wyświetlane, gdy uprawnienia użytkownika według firmy są ograniczane ze względów bezpieczeństwa.
W tej wersji plany stałych wynagrodzeń są wyświetlane, gdy uprawnienia użytkownika według firmy są ograniczane ze względów bezpieczeństwa. Wszystkie ustawienia zabezpieczeń będą obowiązywać, a plany stałych wynagrodzeń będą wyświetlane dla tych firm, dla których użytkownik ma prawo dostępu. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>Nie można usuwać rekordów ofert pracy za pomocą opcji Otwórz w programie Excel w aplikacji Talent
W tej wersji można teraz usuwać rekordy ofert pracy, używając opcji **Otwórz w programie Excel** w aplikacji Talent.

### <a name="upgrade-to-common-data-service"></a>Uaktualnianie do rozwiązania Common Data Service
Zbliżają się terminy uaktualniania do Common Data Service dla aplikacji. Zaloguj się do Centrum administracyjnego usługi Power Apps, aby określić, czy baza danych wymaga uaktualnienia. Aby uzyskać więcej informacji dotyczących terminów i niezbędne kroki w celu uaktualnienia, zobacz [uaktualnienia do Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>Wersja próbna

Aby uzyskać informacje dotyczące włączania funkcji podglądu, zobacz [Dostęp do funkcji podglądu w Microsoft Dynamics 365 Talent](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Zezwalaj na określanie kodów przyczyn dla typów urlopu
Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Aby uzyskać te informacje, pracownicy muszą uwzględnić kod przyczyny we wnioskach o urlop. Ta wersja umożliwia określenie kodów przyczyn skojarzonych z danym typem urlopu i pozwala pracownikom wybrać kod przyczyny we wniosku o urlop.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Konfigurowanie wymogu podania kodu przyczyny podczas przesyłania wniosków o urlop dla określonych typów urlopu
Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. Może to być wymagane na podstawie przepisów prawa w danym kraju/regionie lub ze względu na zasady firmy. Ta wersja oferuje działowi zasobów ludzkich możliwość określenia, które typy urlopów wymagają podania kodu przyczyny. Zasady te będą wymuszane, gdy pracownik prześle wniosek o urlop wymagający podania kodu przyczyny.

## <a name="coming-soon"></a>Wkrótce

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)
W wielu organizacjach menedżerowie ds. wynagrodzenia i świadczeń mogą mieć dostęp tylko do konkretnych rekordów wynagrodzeń. Te rekordy mogą dotyczyć kierowników lub pracowników regionalnych. W przypadku tej zmiany można zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji. Stałe i zmienne plany mogą mieć przypisane role zabezpieczeń, które będą określały dostęp do planów i danych pracowników związanych z planami, takich jak rekordy płac i premii. Tylko role z przyznanym dostępem mogą przetwarzać wynagrodzenia tych pracowników.

###  <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów
25. aktualizacja platformy dla rozwiązania Finance and Operations pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia e-mail do kontaktów w wyniku wyzwolenia przez zdarzenie. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Sprawdzanie zduplikowanych pracowników: zmiany w interfejsie użytkownika
Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.
