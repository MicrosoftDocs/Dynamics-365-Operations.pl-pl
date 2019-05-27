---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (1 października 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
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
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 15b5fd7095a62aa9b7b79ebfcada667959b756aa
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518866"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (1 października 2018 r.)

[!include [banner](includes/banner.md)]

**Kompilacja 8.1.1035.0**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="turn-off-electronic-payment-validation"></a>Wyłączanie sprawdzania poprawności płatności elektronicznych

Sprawdzanie poprawności informacji w płatnościach elektronicznych jest wykonywane po zdefiniowaniu wypłat przelewem bezpośrednim w obszarze roboczym **Samoobsługa pracownika etatowego** (ESS) lub bezpośrednio w formularzu Pracownik. Ta opcja oferuje możliwość usunięcia takiego sprawdzania poprawności, jeśli nie jest ono wymagane dla kwot ani pozostałych wartości. Ta funkcja jest przydatna w przypadku integracji z zewnętrznym systemem listy płac, który ma inne wymagania.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Samoobsługa menedżera — dodawanie celów dla członków zespołu za pośrednictwem kafelka Cele dotyczące wydajności zespołu

W poprzednich wersjach menedżerowie mogą dodawać cele do swoich pracowników indywidualnie za pomocą celów wydajnościowych skojarzonych z poszczególnymi pracownikami. W tej aktualizacji menedżerowie mogą przejść do kafelka **Cele dotyczące wydajności zespołu** i tworzyć nowe cele, wybierając dowolnych spośród swoich bezpośrednich podwładnych.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Samoobsługa menedżera — dodawanie ocen dla członków zespołu za pośrednictwem kafelka Przeglądy wydajności zespołu

W poprzednich wersjach menedżerowie mogą dodawać oceny do swoich pracowników indywidualnie za pomocą ocen skojarzonych z poszczególnymi pracownikami. W tej aktualizacji menedżerowie mogą przejść do kafelka **Przeglądy wydajności zespołu** i tworzyć nowe oceny, wybierając dowolnych spośród swoich bezpośrednich podwładnych.

## <a name="configure-proration-options-by-leave-plan"></a>Konfigurowanie opcji proporcjonalności dla poszczególnych planów urlopów

Organizacje przyznają pulę czasu wolnego/urlopów zależnie od tego, kiedy pracownik rozpoczął i zakończył zatrudnienie. W niektórych organizacjach z chwilą rozpoczęcia zatrudnienia pracownicy otrzymują pełną pulę, a w innych przysługująca długość urlopu jest obliczana proporcjonalnie. W tej wersji dodano nowe opcje umożliwiające wybór sposobu proporcjonalnego określania przyznań i naliczeń dla osób dołączających i opuszczających organizację. Dostępne opcje to: Proporcjonalnie, Pełne naliczanie i Bez naliczania.

## <a name="other-changes"></a>Inne zmiany

-   Zaktualizowano jednostkę Pracownik etatowy — tytuł **Osobiste** można teraz aktualizować za pomocą dodatku programu Excel/obszaru roboczego Zarządzanie danymi.

-   Zmiana w zabezpieczeniach pozwalająca na usunięcie przycisków **Usuń** i **Dezaktywuj** w sekcji informacji płatniczych w obszarze roboczym Samoobsługa pracownika etatowego.

## <a name="known-issue"></a>Znany problem

-   **Problem:** podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. **Obejście:** przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte. Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski w sekcji **Załączniki** będą włączone. (Ten problem zostanie rozwiązany w następnej aktualizacji platformy).
