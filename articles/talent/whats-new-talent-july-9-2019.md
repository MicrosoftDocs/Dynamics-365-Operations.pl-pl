---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (9 lipiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
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
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 99a7e6130d45229011a185087d4872fe34b8224a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897633"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-9-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (9 lipiec 2019)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

#### <a name="job-approvals-appear-on-the-home-page"></a>Zatwierdzenia zadań pojawiają się na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2374.

### <a name="platform-update-28-for-finance-and-operations"></a>Aktualizacja Platform update 28 dla Finance and Operations

Aby uzyskać więcej informacji dotyczących 28. aktualizacji platformy dla rozwiązania Finance and Operations, zobacz [Podgląd funkcji w 28. aktualizacji platformy Dynamics 365 Finance and Operations (lipiec 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Obsługa firm w Common Data Service dla pól niestandardowych 

Pola niestandardowe są obsługiwane przez następujące jednostki: 

- **System stałych wynagrodzeń**
- **Ustawianie punktów odniesienia kompensacji**
- **Linia ustawień punktów odniesienia kompensacji**
- **Kody zarobków dla listy płac**
- **Okres płac**
- **Wydarzenia stałych kompensacji**
- **Siatka wynagrodzeń**

Aby wyświetlić wszystkie zaktualizowane jednostki w Talent:

1. Wybierz **Administrowanie systemem**, następnie wybierz **Łącza**, a następnie wybierz opcję **Konfiguracja Common data service**.
2. Wybierz menu **Nazwa jednostki w usłudze CDS**. Wszystkie wymienione jednostki znajdują się w najnowszej wersji. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Pełna nazwa dodana do jednostki pracownika w Common Data Service

Pole **Imię i nazwisko** zostało dodane do jednostki **Pracownik**.

### <a name="full-time-equivalent-higher-than-10"></a>Ekwiwalent pełnego etatu wyższy niż 1,0

Ostrzeżenie jest wyświetlane w przypadku, gdy wartość większa niż 1,0 zostanie wprowadzona dla pracownika etatowego na danym stanowisku. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>Ostrzeżenie nie jest już wyświetlane na stronie pracownika, jeśli nie ma żadnej przyszłej pracy.

Po przejściu do strony **Pracownik** z listy **Istniejący pracownicy** w obszarze roboczym zarządzanie **Zarządzanie personelem** nie będzie wyświetlany komunikat wskazujący na istnienie przyszłego zatrudnienia. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>Nie można usunąć procesu biznesowego w Talent

Aktywne procesy biznesowe można teraz usuwać w obszarze roboczym **Procesy biznesowe**.

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>Pole saldo już nie zawiera wartości zero w przypadku planów bez naliczania, gdy saldo jest używane jako okres naliczania

Plany skonfigurowane bez naliczania mogą teraz wskazywać saldo.

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Funkcje podglądu są włączone tylko w środowisku testowym

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest **Produkcja**, czy **Piaskownica - środowisko testowe**. Wystąpienia typu **Piaskownica** umożliwiają wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

## <a name="coming-soon-in-core-hr"></a>Już wkrótce w Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Wyświetlanie rozszerzonych informacji o wydajności w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie kierownicy wierszy mogą przypisywać i aktualizować cele wydajności oraz wydawać nowe recenzje, które są wspólnie zarządzane przez ich pracowników Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie. 

### <a name="entities-supporting-custom-fields"></a>Jednostki wspierające pola niestandardowe

Następujące jednostki zostaną włączone dla niestandardowych pól w Common Data Service: 

- **Typ urlopu**
- **Konto bankowe pracownika**
- **Kalendarz pracy**
