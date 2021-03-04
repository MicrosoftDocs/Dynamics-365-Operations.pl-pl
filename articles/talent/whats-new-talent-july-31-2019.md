---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (30 lipiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 311042caf6a391a06c7e2d8c4c2c2f6e1f855437
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462267"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-30-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (30 lipiec 2019)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2409.


### <a name="region-support-for-canada-and-southeast-asia"></a>Obsługa regionu Kanada i Południowo-Wschodnia Azja

Mamy przyjemność poinformować o tym, że rozwiązania Talent od 1 sierpnia 2019 r. będą dostępne w regionach Kanada i Azja Południowo-Wschodnia. Dzięki tej zmianie można tworzyć środowiska w regionach Kanada i Azja, a wszystkie dane Talent będą obsługiwane wyłącznie w tych lokalizacjach. Środowisko w tych nowych regionach można utworzyć, wybierając lokalizację w oknie dialogowym Nowe środowisko i używając tego środowiska do inicjowania obsługi Talent w LCS, zgodnie z opisem [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Migracja danych istniejących projektów z innych regionów do Kanady i Azji nie jest obsługiwana. Tylko nowe projekty mogą zostać zainicjowane do tych nowych obsługiwanych regionów.

### <a name="new-active-positions-list-page"></a>Nowa strona listy aktywnych stanowisk

Dostępne są następujące opcje dla list stanowisk: **Wszystkie stanowiska**, **Aktywne stanowiska**, **Otwarte stanowiska** i **Nieaktywne**. Na nowej stronie **Aktywne stanowiska** wyświetlane są tylko te pozycje, które są otwarte lub wypełnione, które są aktywne na dzień bieżący 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a>Zezwól na dodawanie uczestników kursu do otwartych kursów

Zmiany w tym tygodniu są poprawiają błąd, w którym w przypadku otwartych kursów można było rejestrować tylko raporty bezpośrednie.

### <a name="fte-analysis-displaying-incorrect-fte-number"></a>Analiza pełnego wymiaru czasu wyświetlająca niepoprawny numer pełnego etatu

**Analiza pełnego wymiaru czasu** została poprawiona na karcie **Analizy** dla **Zarządzanie personelem**.

### <a name="final-comments-label-translation"></a>Tłumaczenie etykiety ostatecznych komentarzy

Etykieta **Ostateczne komentarze** zostanie teraz przetłumaczona w formularzu przeglądu.

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Funkcje podglądu są włączone tylko w środowisku testowym

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest **Produkcja**, czy **Piaskownica - środowisko testowe**. Wystąpienia typu **Piaskownica** umożliwiają wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Wyświetlanie rozszerzonych informacji o wydajności w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje. Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]