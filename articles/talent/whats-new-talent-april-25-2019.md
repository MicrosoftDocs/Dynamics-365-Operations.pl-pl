---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (23 kwietnia 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 53faf972759c8f770017fcd3a87920410988e626
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527197"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (23 kwietnia 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2253. Liczby w nawiasach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych
W wydaniu z tego tygodnia następujące jednostki obsługują pola niestandardowe: poziom wynagrodzeń, opcja świadczeń, typ umiejętności i region wynagrodzeń.

### <a name="additional-odata-entities-302992"></a>Dodatkowe jednostki OData (302992)
Poniższe jednostki są obecnie obsługiwane w ramach funkcji OData: doświadczenie zawodowe i wykształcenie pracownika.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Załączniki arkusza wydajności dla menedżerów i pracowników (308248)
W tym wydaniu załączniki są teraz dostępne dla menedżerów i pracowników podczas tworzenia i aktualizowania wpisów w arkuszu wydajności.

### <a name="employee-rehire-flag-always-available-310047"></a>Flaga ponownego zatrudnienia pracownika jest zawsze dostępna (310047)
Opcja ponownego zatrudnienia pracownika jest teraz dostępna do aktualizacji poza procesem zwolnienia. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>Nie można zmienić nazwy **mojej metody płatności** (308815)
Dodano funkcje personalizacji, aby umożliwić zmianę etykiety **Mojej metody płatności** w samoobsłudze pracownika.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>Nie można usunąć wymiarów finansowych dla stanowiska (293908)
Wymiary finansowe można teraz usunąć podczas żądania zmiany istniejącego stanowiska i wymiarów finansowych między granicami firmy. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>Klient nie może publikować danych z powrotem w aplikacji Talent, jeśli otworzy dane w programie Excel (302955)
Ta zmiana eliminuje problem z publikowaniem w przypadku używania tabel pokrewnych.

## <a name="in-preview"></a>Wersja próbna

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Zezwalaj na określanie kodów przyczyn dla typów urlopu
Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.
Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. Może to być spowodowane wymaganiami prawnymi lub polityką firmy. Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich
Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldem.

## <a name="coming-soon"></a>Wkrótce

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Ulepszona funkcja interfejsu użytkownika do sprawdzania zduplikowanych pracowników
Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.
## <a name="known-issues"></a>Znane problemy

### <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów
Aktualizacja platformy 26 dla Finance and Operations pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie.
