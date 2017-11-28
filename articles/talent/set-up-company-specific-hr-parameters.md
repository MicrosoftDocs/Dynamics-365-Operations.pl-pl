---
title: "Konfigurowanie parametrów Zasobów ludzkich specyficznych dla firmy"
description: "Niektóre parametry modułu Zasoby ludzkie (HR) są wspólne dla wielu firm, podczas gdy inne parametry są specyficzne dla firm. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie specyficzne dla firmy."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HRMParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aca20b7a9a56ecef88b466324527650cf6fe34d2
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-company-specific-hr-parameters"></a>Konfigurowanie parametrów Zasobów ludzkich specyficznych dla firmy

[!include[banner](includes/banner.md)]


Niektóre parametry modułu Zasoby ludzkie (HR) są wspólne dla wielu firm, podczas gdy inne parametry są specyficzne dla firm. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie specyficzne dla firmy.

Do ustawiania parametrów Zasobów ludzkich służą dwie strony. W przypadku parametrów współużytkowanych przez firmy, użyj strony **Udostępniane parametry zasobów ludzkich**. W przypadku parametrów specyficznych dla firmy (ustawienie dotyczy tylko jednej firmy), użyj strony **Parametry zasobów ludzkich**. Na stronie **parametrów zasobów ludzkich** ustawienia są podzielone na sześciu kartach:

-   Ogólne
-   Rekrutacja — tej funkcjonalności nie ma w aplikacji Dynamics 365 for Talent
-   Wynagrodzenie
-   Sekwencje identyfikatorów
-   Rozporządzenie dotyczące zwolnień chorobowych i rodzinnych (FMLA)
-   Samoobsługa pracownika

Każda karta zawiera informacje dotyczące jednej firmy. Ustawienia wprowadzone na karcie **Ogólne** definiują wygląd informacji o nieobecności, urazach, chorobach i zatrudnianiu nowych pracowników. Ustawienia na tej karcie definiują także niektóre domyślne wpisy pojawiające się podczas pracy. Karta ta umożliwia wybranie koloru stosowanego do otwartych transakcji nieobecności, zamówienia, w którym są wyświetlane nazwy, arkusza stylów używanego w raportach oraz włączania integracji między kursami szkoleniowymi a rejestracją nieobecności, a także wybranie kodu nieobecności służącego do kontroli tej integracji. Można również określić, jak długo jak długo przechowywać zdarzenia urazów i chorób i określić domyślny numer identyfikacyjny, który jest wyświetlany, kiedy nowy pracownik jest zatrudniony. 

Ustawienia wprowadzone na karcie **rekrutacji** definiują typy dokumentów używanych do korespondencji automatycznie wysyłanej do kandydatów, i projekt rekrutacji używany do obsługi niezamawianych zgłoszeń (które nie dotyczą określonego projektu rekrutacji). Okres zdefiniowany dla wiekowania projektu rekrutacji określa projekty rekrutacji uwzględnione w kafelku **Projekty wiekowania** w obszarze roboczym **Zarządzanie rekrutacją**. Okres zdefiniowany dla ostrzeżenia o ostatecznym terminie zgłoszenia jest używany do wyświetlania projektów rekrutacji, których ostateczny termin zgłoszeń się zbliża i jest określony w kafelku **Zbliża się ostateczny termin zgłoszenia** w obszarze roboczym **Rekrutacja**. 

Ustawienia wprowadzone na karcie **Wynagrodzenie** określają, czy użytkownicy muszą potwierdzać, że chcą zapisać informacje dla systemu wynagrodzeń o stałej lub zmiennej wysokości. W przypadku zaznaczenia pola wyboru **Włącz weryfikację zapisu** za każdym razem, kiedy użytkownik zamknie stronę związaną z wynagrodzeniami, otrzyma wiadomość z zapytaniem, czy chce zapisać rekord. Niektóre strony w module zarządzania wynagrodzeniami nie zezwalają na usuwanie informacji. Dzięki pytaniu użytkowników, czy chcą zapisać informacje, można ograniczyć ilość zapisywanych danych, których potem nie można usunąć. Jeśli pole wyboru **Włącz weryfikację zapisu** nie zostanie zaznaczone, rekordy będą zawsze natychmiast zapisywane, być może zanim użytkownik będzie gotowy. W przypadku korzystania z funkcji zarządzania wydajnością można wybrać model oceniania na karcie **Wynagrodzenie** zamiast modelu przypisanego do systemów wynagrodzeń przy ocenie wydajności. 

### <a name="previously-released-functionality"></a>Wcześniej wydane grupy funkcjonalności
Ustawienia wprowadzone na karcie **Sekwencja numerów** określają sekwencje używane do automatycznego przypisywania identyfikatorów do elementów w module Zasoby ludzkie, takich jak zgłoszenia, rejestracje nieobecności, wyniki procesu wynagrodzenia, numery spraw i terminarze kursów. Aby obsługiwać odwołania numeracji i kody, użyj strony listy **Sekwencje identyfikatorów** (kliknij kolejno opcje **Administrowanie organizacją** &gt; **Sekwencje identyfikatorów** &gt; **Sekwencje identyfikatorów**).

### <a name="if-youre-using-dynamics-365-for-talent"></a>Jeśli używasz programu Dynamics 365 for Talent
Ustawienia wprowadzone na karcie **Sekwencja numerów** określają sekwencje używane do automatycznego przypisywania identyfikatorów do elementów w module Zasoby ludzkie, takich jak zgłoszenia, rejestracje nieobecności, wyniki procesu wynagrodzenia, numery spraw i terminarze kursów. Aby obsługiwać odwołania numeracji i kody, użyj strony listy **Sekwencje identyfikatorów** (kliknij kolejno opcje **Administrowanie systemem** &gt; **karta Linki** &gt; **Sekwencje identyfikatorów** &gt; **Sekwencje identyfikatorów**). 

Ustawienia wprowadzone na karcie **FMLA** określają, ile godzin pracownik musi pracować, aby otrzymać świadczenia FMLA, wymagany staż pracy i datę zatrudnienia konieczną do określenia stażu pracy. Ustawienia te definiują również liczbę godzin FMLA, do których pracownik jest upoważniony oraz kalendarz nieobecności FMLA używany do obliczenia, ile godzin FMLA pracownik wykorzystał. Karta **FMLA** jest dostępna tylko dla firm w Stanach Zjednoczonych. 

**Uwaga:** liczba przepracowanych godzin nie może przekroczyć 1250, a staż pracy nie może przekroczyć 12 miesięcy. Te maksymalne wartości są zgodne z prawem federalnym w Stanach Zjednoczonych. Ustawienia na karcie **Samoobsługa pracownika** określają informacje,jakie może wprowadzać menedżer w imieniu pracowników.

<a name="see-also"></a>Informacje dodatkowe
--------

[Konfigurowanie parametrów modułu Zasoby ludzkie w wielu firmach](set-up-hr-parameters-across-legal-entities.md)




