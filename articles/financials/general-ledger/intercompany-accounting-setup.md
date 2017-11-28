---
title: "Konfiguracja księgowania międzyfirmowego"
description: "W tym temacie wyjaśniono, jak skonfigurować księgowanie międzyfirmowe, co pozwoli używać arkuszy międzyfirmowych do alokacji księgi i arkuszy finansowych, takich jak arkusze dzienne, arkusze faktur od dostawców i arkusze płatności."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 48e0b00e2a9bd1a1387780747e1976bd386200eb
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="intercompany-accounting-setup"></a>Konfiguracja księgowania międzyfirmowego

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak skonfigurować księgowanie międzyfirmowe, co pozwoli używać arkuszy międzyfirmowych do alokacji księgi i arkuszy finansowych, takich jak arkusze dzienne, arkusze faktur od dostawców i arkusze płatności.

Arkusze międzyfirmowe mogą być tworzone w różnych scenariuszach, np. dla arkuszy dziennych, arkuszy faktur od dostawców, alokacji księgi czy płatności scentralizowanych. Aby te scenariusze były dostępne, należy skonfigurować księgowanie międzyfirmowe.

## <a name="define-main-accounts"></a>Definiowanie kont głównych
Najpierw należy utworzyć międzyfirmowe konta główne na potrzeby zapisów księgowych Finansowanie i Należne. Dobrze jest używać niepowtarzalnych kont głównych dla każdej firmy, aby uprościć proces uzgadniania i usuwania międzyfirmowych zapisów księgowych. Jeśli używany jest wymiar partnera handlowego lub kontrahenta do identyfikacji strony międzyfirmowej, można zdefiniować ten wymiar jako wymiar stały na koncie głównym zdefiniowanym w module Księgowanie międzyfirmowe. Po skonfigurowaniu kont głównych trzeba na stronie **Konto główne** w polu **Typ konta głównego** ustawić wartość **Bilans**.

## <a name="define-journal-names"></a>Definiowanie nazw arkuszy
Następnie należy zdefiniować nazwę arkusza. Na stronie **Nazwy arkuszy** w polu **Typ arkusza** ustaw wartość **Codziennie**. Dobrze jest użyć nazwy określonego arkusza na potrzeby księgowania międzyfirmowego.

## <a name="define-intercompany-accounting-setup"></a>Definiowanie konfiguracji księgowania międzyfirmowego
Strona **Księgowanie międzyfirmowe** jest używana do tworzenia par firm, które mogą zawierać między sobą transakcje. Konfiguracja księgowania międzyfirmowego jest udostępniana, a więc widoczna ze wszystkich firm. Tworząc nową parę firm, upewnij się, że wiesz, która firma ma być źródłowa, a która docelowa. Podczas zawierania transakcji międzyfirmowej to transakcja decyduje, która firma jest źródłowa, a która docelowa. Na przykład w księgowaniu międzyfirmowym ustawiono firmy USMF (źródłowa) i USSI (docelowa). Jeżeli użytkownik jest aktywny w firmie USSI i zawrze transakcję międzyfirmową z firmą USMF, transakcja nie zostanie zaksięgowana, ponieważ w księgowaniu międzyfirmowym firma USMF została zdefiniowana tylko jako źródłowa. Jeśli którakolwiek firma może inicjować transakcję, należy utworzyć drugą parę firm z odwrotną konfiguracją. 

Skonfiguruj opcje **Konto debetowe (należne od)** i **Konto kredytowe (należne dla)** dla obu firm — źródłowej i docelowej. W polu **Nazwa arkusza** określ, który arkusz będzie używany podczas tworzenia transakcji w firmie docelowej. Arkusz dla firmy źródłowej jest już znany, ponieważ został wybrany przez użytkownika podczas tworzenia transakcji międzyfirmowej. 

Wreszcie określ, w której firmie zostaną zaksięgowane kwoty pomocnicze, takie jak rabaty gotówkowe lub zrealizowane dodatnie/ujemne różnice kursowe w płatnościach scentralizowanych. 

Relację odwrotną można łatwo można skonfigurować na stronie **Księgowanie międzyfirmowe** poprzez kliknięcie przycisku **Utwórz relację wzajemną** po utworzeniu pierwszej pary firm. Podczas tworzenia pary z konfiguracją odwrotną informacje firmy docelowej są kopiowane do firmy źródłowej i na odwrót. Arkusz zdefiniowany dla firmy docelowej pozostaje bez zmian. Większość organizacji używa tej samej konwencji nazewnictwa dla nazw swoich arkuszy, więc nazwa arkusza się nie zmieni. Jeśli nazwa arkusza będzie inna, w polu pojawi się ostrzeżenie informujące, że arkusz nie istnieje i można wybrać inny arkusz.




