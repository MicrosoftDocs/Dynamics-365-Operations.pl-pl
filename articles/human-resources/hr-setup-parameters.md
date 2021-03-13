---
title: Konfigurowanie parametrów modułu Human Resources
description: Niektóre parametry modułu Human Resources są wspólne dla wielu firm, podczas gdy inne parametry są specyficzne dla firm. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie specyficzne dla firmy.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 131606ebaff49a2c63d22bcfdb5e523f4df87ec6
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129132"
---
# <a name="configure-human-resources-parameters"></a>Konfigurowanie parametrów modułu Human Resources

Niektóre parametry modułu Zasoby ludzkie (HR) są wspólne dla wielu firm, podczas gdy inne parametry są specyficzne dla firm. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie specyficzne dla firmy.

Do ustawiania parametrów Zasobów ludzkich służą dwie strony. W przypadku parametrów współużytkowanych przez firmy, użyj strony **Udostępniane parametry zasobów ludzkich**. W przypadku parametrów specyficznych dla firmy (ustawienie dotyczy tylko jednej firmy), użyj strony **Parametry zasobów ludzkich**. Na stronie **parametrów zasobów ludzkich** ustawienia są podzielone na sześciu kartach:

-   Ogólne
-   Rekrutacja — tej funkcjonalności nie ma w aplikacji Dynamics 365 Human Resources
-   Kompensata
-   Sekwencje identyfikatorów
-   Rozporządzenie dotyczące zwolnień chorobowych i rodzinnych (FMLA)
-   Samoobsługa pracownika

Każda karta zawiera informacje dotyczące jednej firmy. Ustawienia wprowadzone na karcie **Ogólne** definiują wygląd informacji o nieobecności, urazach, chorobach i zatrudnianiu nowych pracowników. Ustawienia na tej karcie definiują także niektóre domyślne wpisy pojawiające się podczas pracy. Karta ta umożliwia wybranie koloru stosowanego do otwartych transakcji nieobecności, zamówienia, w którym są wyświetlane nazwy, arkusza stylów używanego w raportach oraz włączania integracji między kursami szkoleniowymi a rejestracją nieobecności, a także wybranie kodu nieobecności służącego do kontroli tej integracji. Można również określić, jak długo jak długo przechowywać zdarzenia urazów i chorób i określić domyślny numer identyfikacyjny, który jest wyświetlany, kiedy nowy pracownik jest zatrudniony. 

Ustawienia wprowadzone na karcie **rekrutacji** definiują typy dokumentów używanych do korespondencji automatycznie wysyłanej do kandydatów, i projekt rekrutacji używany do obsługi niezamawianych zgłoszeń (które nie dotyczą określonego projektu rekrutacji). Okres zdefiniowany dla wiekowania projektu rekrutacji określa projekty rekrutacji uwzględnione w kafelku **Projekty wiekowania** w obszarze roboczym **Zarządzanie rekrutacją**. Okres zdefiniowany dla ostrzeżenia o ostatecznym terminie zgłoszenia jest używany do wyświetlania projektów rekrutacji, których ostateczny termin zgłoszeń się zbliża i jest określony w kafelku **Zbliża się ostateczny termin zgłoszenia** w obszarze roboczym **Rekrutacja**. 

Ustawienia wprowadzone na karcie **Wynagrodzenie** określają, czy użytkownicy muszą potwierdzać, że chcą zapisać informacje dla systemu wynagrodzeń o stałej lub zmiennej wysokości. W przypadku zaznaczenia pola wyboru **Włącz weryfikację zapisu** za każdym razem, kiedy użytkownik zamknie stronę związaną z wynagrodzeniami, otrzyma wiadomość z zapytaniem, czy chce zapisać rekord. Niektóre strony w module zarządzania wynagrodzeniami nie zezwalają na usuwanie informacji. Dzięki pytaniu użytkowników, czy chcą zapisać informacje, można ograniczyć ilość zapisywanych danych, których potem nie można usunąć. Jeśli pole wyboru **Włącz weryfikację zapisu** nie zostanie zaznaczone, rekordy będą zawsze natychmiast zapisywane, być może zanim użytkownik będzie gotowy. W przypadku korzystania z funkcji zarządzania wydajnością można wybrać model oceniania na karcie **Wynagrodzenie** zamiast modelu przypisanego do systemów wynagrodzeń przy ocenie wydajności. 

### <a name="previously-released-functionality"></a>Wcześniej wydane grupy funkcjonalności

Ustawienia wprowadzone na karcie **Sekwencja numerów** określają sekwencje używane do automatycznego przypisywania identyfikatorów do elementów w module Zasoby ludzkie, takich jak zgłoszenia, rejestracje nieobecności, wyniki procesu wynagrodzenia, numery spraw i terminarze kursów. Aby obsługiwać odwołania numeracji i kody, użyj strony listy **Sekwencje identyfikatorów** (kliknij kolejno opcje **Administrowanie organizacją** &gt; **Sekwencje identyfikatorów** &gt; **Sekwencje identyfikatorów**).

> [!NOTE]
> Liczba przepracowanych godzin nie może przekroczyć 1250, a staż pracy nie może przekroczyć 12 miesięcy. Te maksymalne wartości są zgodne z prawem federalnym w Stanach Zjednoczonych. Ustawienia na karcie **Samoobsługa pracownika etatowego** określają informacje,jakie mogą wprowadzać menedżerowie w imieniu swoich pracowników.
