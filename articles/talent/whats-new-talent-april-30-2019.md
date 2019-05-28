---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (30 kwietnia 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
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
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 112146ac46193e37b33bf429dc5a359f8cfaca94
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1505382"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-april-30-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (30 kwietnia 2019)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2270. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="provide-feedback"></a>Prześlij opinię

Opcja dostarczania opinii znajduje się w menu **Pomoc** (**?**) w aplikacji Talent. To menu umożliwia dostęp do następujących zasobów:

- Opinii
- Pomoc
- Rozpoczynanie pracy
- Pomoc techniczna
- Pomysły
- Informacje

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>Ulepszona funkcja interfejsu użytkownika do wykrywania zduplikowanych pracowników

Ta zmiana powoduje, że duplikaty są teraz wykrywane podczas ustawiania pól nazw, a wskaźnik stanu pokazuje liczbę wykrytych duplikatów. Podane łącze otwiera stronę, na której można ocenić, czy należy zastosować jeden z duplikatów. Aby uniknąć zakłóceń we wprowadzaniu danych, strona duplikatów nie jest otwierana automatycznie. Trzeba kliknąć łącze, aby otworzyć stronę.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

W wydaniu z tego tygodnia następujące jednostki obsługują obecnie pola niestandardowe: zatrudnienie, typ świadczenia i cykl płac.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Wystąpił błąd podczas przypisywania listy kontrolnej odłączania (299877)

Ta zmiana koryguje komunikat o błędzie wyświetlany po przypisaniu listy kontrolnej odłączania do pracownika poza procesem zwolnienia.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>Łącze do listy pracowników, którzy odeszli otwiera dane dla niewłaściwego pracownika (309939)

Ta zmiana koryguje problem występujący podczas ponownego zatrudniania pracownika z innej firmy i próby przejścia do pracownika z listy pracowników, którzy odeszli.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>Karta wynagrodzenia pracownika za samoobsługę nie pokazuje wartości podsumowań w przypadku włączenia zaawansowanych zabezpieczeń (315231)

Ta zmiana powoduje usunięcie problemu, który występuje w przypadku korzystania z zaawansowanych zabezpieczeń wynagrodzeń. Gdy włączone jest zaawansowane zabezpieczenie, karta samoobsługi pracowników wyświetla teraz podsumowanie kwot wynagrodzeń dla pracowników i menedżerów. Przed tą zmianą wartości podsumowania były wyświetlane jako 0 (zero).

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>W przypadku utworzenia w systemie Common Data Service stanowiska bez tytułu nie zostanie utworzone stanowisko w aplikacji Talent (314562)

Zmiany z tego tygodnia umożliwiają usunięcie problemu, który występuje podczas tworzenia stanowisk bez podania tytułu w Common Data Service.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Komunikat o błędzie we wpisach arkusza wydajności w samoobsłudze pracownika (314134)

Ta zmiana koryguje problem występujący podczas dołączania celów wydajności do wpisów w arkuszu wydajności w samoobsłudze pracownika.

## <a name="in-preview"></a>Wersja próbna

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Zezwalaj na określanie kodów przyczyn dla typów urlopu

Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.

Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa. Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich

Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldem.

## <a name="coming-soon"></a>Wkrótce

### <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów

Aktualizacja platformy 26 pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie.
