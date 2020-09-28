---
title: Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów
description: Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80ec8fed2094025ef31114a229c35bee1cd1033b
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759335"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów

[!include [banner](../../includes/banner.md)]

Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów. Nagranie wykorzystuje dane firmy demonstracyjnej USP2.


## <a name="create-a-policy"></a>Tworzenie zasady
1. Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady alokacji kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa zasad wpisz wartość.
4. W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję Organizacja.  
5. W polu Wymiar statystyczny wprowadź lub wybierz wartość.
6. Kliknij przycisk Zapisz.

## <a name="create-allocation-rules"></a>Tworzenie reguł alokacji
1. Kliknij przycisk Nowy.
2. Na liście oznacz wybrany wiersz.
3. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
4. W polu Zachowanie kosztów wybierz wartość „Suma”.
5. W polu Podstawa alokacji wprowadź lub wybierz wartość.
6. Kliknij przycisk Nowy.
7. Na liście oznacz wybrany wiersz.
8. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
9. W polu Zachowanie kosztów wybierz wartość „Suma”.
10. W polu Podstawa alokacji wprowadź lub wybierz wartość.
11. Kliknij przycisk Nowy.
12. Na liście oznacz wybrany wiersz.
13. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
14. W polu Zachowanie kosztów wybierz wartość „Suma”.
15. W polu Podstawa alokacji wprowadź lub wybierz wartość.
    * Kontynuuj, aż utworzysz wszystkie reguły.  
16. Kliknij przycisk Zapisz.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Przypisywanie zasady do jednostki kontroli kosztów
1. Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Ważne od daty księgowania wpisz datę.
    * Reguły mają daty obowiązywania. Użytkownik lub system może wygasić regułę, jeśli zostanie utworzona nowsza wersja.  
5. W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.
6. Kliknij przycisk Zapisz.

