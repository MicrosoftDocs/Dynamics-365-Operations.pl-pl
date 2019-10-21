---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (11 czerwiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b06dc0556bd1461573cd56abed602d72333a3f39
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023937"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-11-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (11 czerwiec 2019)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="search-engine-optimization-for-job-posts"></a>Optymalizacja wyszukiwarki zadań

Po włączeniu **Optymalizacja dla wyszukiwarki** w centrum administracyjnym Dynamics 365 Talent: Attract, Attract informuje interfejs programowania aplikacji do indeksowania za pomocą usługi Google Indexing Interface (API) do przeszukiwania strony sieci Web przy każdej aktywacji i publikacji nowego zadania lub aktualizacji istniejącego zadania. W ten sposób zadanie będzie wyświetlane w wynikach wyszukiwania w usłudze Google i innych aparatach wyszukiwania.

Podobnie, za każdym razem, gdy niezaksięgujesz zadanie, przyciągnie do interfejsu API indeksowania powoduje, że niezaksięgowane zadanie przestanie pojawiać się w wynikach wyszukiwania.

> [!NOTE]
> Przeszukiwarki sieci Web nie mają zdefiniowanego czasu na przeszukiwanie stron sieci Web ani na aktualizowanie wyników wyszukiwania.

## <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Zatwierdzenia zadań pojawiają się na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2337.

### <a name="platform-update-27-for-finance-and-operations"></a>Aktualizacja Platform update 27 dla Finance and Operations

Aby uzyskać więcej informacji dotyczących 27. aktualizacji platformy dla rozwiązania Finance and Operations, zobacz [Podgląd funkcji w 27. aktualizacji platformy Dynamics 365 Finance and Operations (czerwiec 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).

### <a name="feature-management-workspace-in-talent"></a>Obszar roboczy zarządzania funkcjami w Talencie

Obszar roboczy **Zarządzanie funkcjami** w module **Administracja systemu** umożliwia wyświetlanie, włączanie, wyłączanie i planowanie funkcji, które zostały dostarczone w każdym wydaniu. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego **Zarządzanie funkcjami**, aby włączyć je i wyświetlić dokumentację dla nich.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

Jednostka agencji wydającej obsługuje teraz pola niestandardowe.

### <a name="new-common-data-service-entities"></a>Nowe Common Data Service jednostki

Jednostka Grupy zadań została dodana.

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Funkcje wersji Preview będą włączone tylko w środowiskach piaskownicy

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Podczas zastrzegania nowej instancji talentów można wskazać, czy typem wystąpienia jest Produkcja, czy Piaskownica - środowisko testowe. Typ instancji Piaskownica umożliwia wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

## <a name="coming-soon-in-core-hr"></a>Już wkrótce w Core HR

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a>Wyświetlanie rozszerzonych informacji o wydajności raportu w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje. Ponadto menedżerowie etatowi i ich pracownicy mogą utrzymywać i aktualizować arkusze wydajności, aby zagwarantować płynność procesu oceny wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Pracownicy, menedżerowie i dział personalny będą mogli drukować przegląd wydajności pracownika.
