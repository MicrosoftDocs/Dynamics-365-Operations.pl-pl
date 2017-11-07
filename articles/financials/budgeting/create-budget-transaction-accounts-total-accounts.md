---
title: "Tworzenie budżetu z kont transakcji i kont sum"
description: "Ten artykuł zawiera omówienie procesu tworzenia budżetów na podstawie kont sum. Ponadto wyjaśnia, jak włączyć kontrolę budżetu dla kont sum, jeśli kontrola budżetu jest wymagana."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fd6dc5173fd37f0257c98c1a41f3e6ce40b5b680
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Tworzenie budżetu z kont transakcji i kont sum

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie procesu tworzenia budżetów na podstawie kont sum. Ponadto wyjaśnia, jak włączyć kontrolę budżetu dla kont sum, jeśli kontrola budżetu jest wymagana.

Dokumenty wpisowe zarówno planu budżetu, jak i rejestru budżetu umożliwiają tworzenie budżetu na kontach głównych z typem **Suma**. Wartości rzeczywiste mogą być księgowane tylko na kontach głównych transakcji. 

Do obsługi okresowego procesu **Generowanie planu budżetu na podstawie księgi głównej** na karcie **Źródło** możesz określić typ konta głównego **Suma** jako kryterium. W tym przypadku każde konto główne będzie objęte docelowym planem budżetu, a kwota będzie równa łącznej kwocie w zakresie dat dla wybranych kont głównych. 

Można uaktywnić kontrolę budżetu dla kont głównych typu **Suma**. Ta funkcja jest obsługiwana za pomocą grup budżetu. Dla każdego konta głównego sum budżet, który ma być kontrolowany w grupie budżetu, musi być utworzony na stronie **Konfiguracja kontroli budżetu**. Zdefiniowane kryteria muszą obejmować konto główne sum oraz zakres kont. Aby przyspieszyć proces tworzenia grup budżetu, użytkownik może skorzystać z jednostki danych grup Kontrola budżetu. 

Jeśli budżet używany jest przy tworzeniu raportów, na przykład w sprawozdaniu finansowym, suma budżetów dla konta sum zawiera następujące kwoty:

-   Budżety utworzone z każdego konta księgowego transakcji w interwale konta sum.
-   Kwota budżetu wprowadzona bezpośrednio na koncie sum.

Dlatego możliwe jest tworzenie oddzielnych budżetów dla najważniejszych kont transakcji w interwale konta sum i dodawanie pozostałych kwot budżetów do konta sum.




