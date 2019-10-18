---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (6 maja 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6a4571abdb0e104af0a0657c75bf5a6b5764345a
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023868"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-6-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (6 maja 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="select-optional-documents-upon-offer-creation"></a>Wybierz opcjonalne dokumenty po utworzeniu oferty

Po wybraniu szablonu pakietu oferty Attract wyświetla teraz monit o wybranie odpowiednich, opcjonalnych dokumentów z tego szablonu pakietu. Podczas przygotowywania oferty można dodawać inne opcjonalne dokumenty.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2282. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-26-for-finance-and-operations"></a>Aktualizacja Platform update 26 dla Finance and Operations

Aby uzyskać więcej informacji dotyczących 26. aktualizacji platformy dla rozwiązania Finance and Operations, zobacz [Podgląd funkcji w 26. aktualizacji platformy Dynamics 365 Finance and Operations (maj 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

W wydaniu z tego tygodnia następujące jednostki obsługują obecnie niestandardowe pola: częstotliwość obliczania świadczeń, stawka obliczania świadczeń, typ świadczenia, kalendarz pracy, dzień wolny, cykl płac i typy identyfikacji pracowników.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Pozostawienie rejestracji grupowej przy zmianie podstawy warstwy na „Data stażu pracy” nie powoduje odświeżenia początkowej stawki naliczania (318526)

Po grupowym zarejestrowaniu pracowników i zmianie podstawy warstwy, początkowe naliczenie będzie teraz odzwierciedlać wybraną podstawę warstwy.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>Przepływ pracy pokazujący zduplikowane symbole zastępcze (313636)

Zmiany w tej wersji eliminują duplikowanie symboli zastępczych, gdy są wysyłane powiadomienia dotyczące przepływu pracy.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>Pola wymiaru nie są aktualizowane, gdy jest używane polecenie „Otwórz w programie Excel” (176261)

W tej wersji można teraz zaktualizować wymiar finansowy za pomocą polecenia **Otwórz w programie Excel** ze strony **pracownik**. 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>Adres pracownika utworzony w Common Data Service nie jest zsynchronizowany z aplikacją Talent (317555)

Wraz z tą zmianą adresy utworzone w Common Data Service są aktualizowane w aplikacji Talent: Core HR.


## <a name="in-preview"></a>Wersja próbna

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nowa strona do sprawdzania poprawności danych hierarchii stanowisk

Zasoby ludzkie (HR) i administratorzy mogą teraz sprawdzać hierarchię kadry kierowniczej dla wszystkich odwołań cyklicznych, które mogłyby zostać przypadkowo zaimportowane. Dostęp do tej nowej strony można uzyskać z menu **Administracja organizacyjna > Łącza > Stanowiska > Sprawdzanie poprawności hierarchii stanowisk**.

### <a name="specify-reason-codes-on-leave-types"></a>Określ kody przyczyn dla typów urlopów

Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.

Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa. Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich

Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldem.

## <a name="coming-soon"></a>Wkrótce

### <a name="indicate-instance-type-when-provisioning-talent"></a>Wskaż typ wystąpienia podczas inicjowania obsługi administracyjnej w aplikacji Talent

Podczas inicjowania obsługi nowego wystąpienia aplikacji Talent można wskazać, czy typ wystąpienia to **produkcja** czy **piaskownica**, co pozwala na wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia produkcji. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia piaskownicy, skontaktuj się z pomocą techniczną, aby zainicjować żądanie zmiany.
