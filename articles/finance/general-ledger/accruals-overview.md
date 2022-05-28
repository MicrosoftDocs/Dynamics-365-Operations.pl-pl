---
title: Przegląd naliczeń
description: W tym temacie opisano koncepcję naliczeń oraz sposób ich konfigurowania i tworzenia transakcji.
author: aprilolson
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14131"
- intro-internal
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62b56e698d3d9eeec08824eb799d74a8c6792ea7
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735240"
---
# <a name="accruals-overview"></a>Przegląd naliczeń

[!include [banner](../includes/banner.md)]

W tym temacie opisano koncepcję naliczeń oraz sposób ich konfigurowania i tworzenia transakcji.

Naliczenia są używane w księgowości memoriałowej do śledzenia przychodu rozpoznawanego w okresie, w którym został zarobiony, a nie w momencie otrzymania płatności, oraz do śledzenia wydatków (kosztów), które są rozpoznawane, gdy się pojawiają, a nie kiedy zostanie zrealizowana płatność.

## <a name="accrual-schemes"></a>Schematy naliczania
Schematy naliczania są używane do ustawiania odroczonych przychodów i kosztów, a ten sam schemat można wykorzystywać i do kosztów i do przychodów. Naliczenia finansowe umożliwiają ponowne rozdzielenie kosztów lub przychodów wiersza arkusza, tak aby były rozpoznawane w odpowiednich okresach. Na stronie **schematu naliczania** można określić konta debetowe i kredytowe, które będą używane po zastosowaniu schematu naliczania.

-   **Debetowe** — zdefiniowane konto główne zostanie zastąpione kontem głównym strony debetowej w wierszu załącznika arkusza. To konto będzie używane także do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.
-   **Kredytowe** — zdefiniowane konto główne zostanie zastąpione kontem głównym strony kredytowej w wierszu załącznika arkusza. To konto będzie używane także do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.

Po ustaleniu, które konta należy zastosować, można określić sposób tworzenia numeru załącznika podczas tworzenia transakcji naliczania. Można również określić, jak często występują transakcje, ile razy transakcje są tworzone i kiedy są księgowane. Po utworzeniu schematu naliczania, można go używać w niektórych arkuszach, stosując funkcję Naliczenia finansowe.

## <a name="ledger-accruals"></a>Naliczenia finansowe
Po wprowadzeniu arkusza można kliknąć opcję **Naliczenia finansowe** w menu **Funkcje**. Następnie, po wybraniu schematu naliczania, zostanie wyświetlona kwota podstawy z arkusza, która zostanie rozłożona w okresie zgodnie ze schematem naliczania. Na przykład jeśli płacisz ubezpieczenie pracownika za cały rok w styczniu, a kwota ubezpieczenia wynosi 12 000, trzeba wykazać ten wydatek w każdym miesiącu. Można wybrać datę początkową. Można również określić, czy naliczana kwota, jest oparta na koncie lub koncie przeciwstawnym. Po dokonaniu wyboru kliknij przycisk **Transakcje**, aby wyświetlić wszystkie transakcje utworzone na podstawie schematu naliczania. Na przykład jeśli podzielisz kwotę ubezpieczenia 12 000 na rok, zobaczysz 1000 w każdym miesiącu. Po zaksięgowaniu arkusza można przeglądać transakcje za pomocą strony zapytań **Transakcje na załączniku**. Jeśli nie można zastosować schematu naliczania (na przykład gdy transakcja dotyczy faktury do zamówienia sprzedaży lub faktury do zamówienia zakupu), można zwrócić przedpłaconą kwotę i potrącić kwotę wydatku. Następnie można wybrać **przeciwstawne**, jeśli stosujesz schemat naliczania.


Aby uzyskać więcej informacji, zobacz [Tworzenie schematów naliczania](tasks/create-accrual-schemes.md) i [Tworzenie transakcji naliczeń finansowych](tasks/create-ledger-accrual-transactions.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
