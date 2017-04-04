---
title: "Przegląd naliczeń"
description: "W tym artykule opisano koncepcję naliczeń oraz sposób ich konfigurowania i tworzenia transakcji."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 328a4a7bef32ee8634e4a9f4854ebe78fcc99f6d
ms.lasthandoff: 03/31/2017


---

# <a name="accruals-overview"></a>Przegląd naliczeń

W tym artykule opisano koncepcję naliczeń oraz sposób ich konfigurowania i tworzenia transakcji.

Naliczenia są używane w księgowości memoriałowej do śledzenia przychodu rozpoznawanego w okresie, w którym został zarobiony, a nie w momencie otrzymania płatności, oraz do śledzenia wydatków (kosztów), które są rozpoznawane, gdy się pojawiają, a nie kiedy zostanie zrealizowana płatność.

## <a name="accrual-schemes"></a>Schematy naliczania
Schematy naliczania są używane do ustawiania odroczonych przychodów i kosztów, a ten sam schemat można wykorzystywać i do kosztów i do przychodów. Naliczenia finansowe umożliwiają ponowne rozdzielenie kosztów lub przychodów wiersza arkusza, tak aby były rozpoznawane w odpowiednich okresach. Na stronie **schematu naliczania** można określić konta debetowe i kredytowe, które będą używane po zastosowaniu schematu naliczania.

-   **Debetowe** — zdefiniowane konto główne zostanie zastąpione kontem głównym strony debetowej w wierszu załącznika arkusza. To konto będzie używane także do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.
-   **Kredytowe** — zdefiniowane konto główne zostanie zastąpione kontem głównym strony kredytowej w wierszu załącznika arkusza. To konto będzie używane także do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.

Po ustaleniu, które konta należy zastosować, można określić sposób tworzenia numeru załącznika podczas tworzenia transakcji naliczania. Można również określić, jak często występują transakcje, ile razy transakcje są tworzone i kiedy są księgowane. Po utworzeniu schematu naliczania, można go używać w niektórych arkuszach, stosując funkcję Naliczenia finansowe.

## <a name="ledger-accruals"></a>Naliczenia finansowe
Po wprowadzeniu arkusza można kliknąć opcję **Naliczenia finansowe** w menu **Funkcje**. Następnie, po wybraniu schematu naliczania, zostanie wyświetlona kwota podstawy z arkusza, która zostanie rozłożona w okresie zgodnie ze schematem naliczania. Na przykład jeśli płacisz ubezpieczenia pracownika przez cały rok w styczniu, a kwota jest 12 000, użytkownik musi rozpoznawać związanymi z tym wydatkami każdego miesiąca. Można wybrać datę rozpoczęcia. Można również określić, czy naliczana kwota, jest oparta na koncie lub koncie przeciwstawnym. Po dokonaniu wyboru kliknij przycisk **transakcji** do wyświetlania wszystkich transakcji, które zostały utworzone na podstawie schematu naliczania. Na przykład jeśli 12 000 w koszty ubezpieczenia jest rozłożone w ciągu roku, zobaczysz 1000 dla każdego miesiąca. Po zaksięgowaniu dziennika transakcji można wyświetlić przy użyciu **transakcje na załączniku** strony dochodzenia. Jeśli nie można zastosować schematu naliczania, (na przykład, gdy chodzi o faktury zamówienia sprzedaży lub faktury dla zamówienia zakupu), należy kwotę przedpłaty i po stronie debetowej kwota wydatków. Następnie można wybrać **przeciwstawne**, jeśli stosujesz schemat naliczania.


