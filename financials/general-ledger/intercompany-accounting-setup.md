---
title: "Ustawienia księgowania międzyfirmowego"
description: "W tym temacie omówiono konfigurowanie księgowania międzyfirmowego, dzięki czemu można używać dzienniki transakcji międzyfirmowych alokacji księgi i arkusze finansowe, takie jak arkuszy dziennych, arkuszy faktur od dostawcy i arkusze płatności."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Ustawienia księgowania międzyfirmowego

W tym temacie omówiono konfigurowanie księgowania międzyfirmowego, dzięki czemu można używać dzienniki transakcji międzyfirmowych alokacji księgi i arkusze finansowe, takie jak arkuszy dziennych, arkuszy faktur od dostawcy i arkusze płatności.

Dzienniki transakcji międzyfirmowych mogą być tworzone w różnych scenariuszach, takich jak dla arkuszy dziennych, arkuszy faktur od dostawcy, alokacjach finansów i płatności scentralizowane. Aby te scenariusze były dostępne, należy skonfigurować księgowanie międzyfirmowe.

## <a name="define-main-accounts"></a>Definiowanie kont głównych
Najpierw należy utworzyć międzyfirmowe konta główne na potrzeby zapisów księgowych Finansowanie i Należne. Dobrze jest używać niepowtarzalnych kont głównych dla każdej firmy, aby uprościć proces uzgadniania i usuwania międzyfirmowych zapisów księgowych. Jeśli używasz partnerem handlowym lub odpowiednik wymiaru do identyfikowania międzyfirmowe ze stron tego wymiaru można zdefiniować jako stały wymiar na koncie głównym, który jest zdefiniowany w księgowości międzyfirmowej. Podczas konfigurowania konta główne, należy ustawić **typu konta głównego** na **bilans** na **konta główne** strony.

## <a name="define-journal-names"></a>Definiowanie nazw arkuszy
Następnie należy zdefiniować nazwę arkusza. Ustaw **typu arkusza** pola do **codziennie** na **nazwy arkuszy** strony. Dobrze jest użyć nazwy określonego arkusza na potrzeby księgowania międzyfirmowego.

## <a name="define-intercompany-accounting-setup"></a>Zdefiniuj ustawienia księgowania międzyfirmowego
**Księgowania międzyfirmowego** strony jest używany do tworzenia par podmiotów prawnych, które mogą między sobą. Ustawienia księgowania międzyfirmowego jest udostępniony, więc Instalator jest widoczne z poziomu wszystkie podmioty prawne. Tworząc nową parę podmiot prawny, upewnij się, że są świadomi który podmiot jest zdefiniowany jako firmę źródłową w porównaniu do firmy docelowej. Podczas wprowadzania transakcji międzyfirmowych, transakcji określa, który podmiot jest inicjowanie lub pochodzący z transakcji. Na przykład księgowania międzyfirmowego jest skonfigurować dla USMF (pochodzące z) i USSI (docelowy). Jeżeli użytkownik jest aktywny w USSI i wchodzi transakcja międzyfirmowa USMF, transakcja nie zostanie zaksięgowane ponieważ księgowania międzyfirmowego jest definiowana tylko dla USMF jest inicjatorem. Każda firma może pochodzić transakcji, należy utworzyć drugi parę podmiot prawny dla wzajemnego Instalatora. 

Wybierz **konto debetowe (należnej od)** i **konto kredytowe (ze względu na)** dla podmiotu prawnego zarówno początkowym i docelowym. Zdefiniować, które **nazwy arkusza** będą używane podczas tworzenia transakcji w firmie docelowej. Arkusz dla firmę źródłową jest już znany, ponieważ jest on wybrany przez użytkownika podczas tworzenia transakcji międzyfirmowych. 

Wreszcie wybierz, który podmiot otrzyma księgowania kwot, takich jak rabatu gotówkowego lub zrealizowane różnice kursowe na potrzeby płatności scentralizowanych pomocniczych. 

Wzajemne relacje można łatwo można ustawić na **księgowania międzyfirmowego** stronę za pomocą **tworzenie wzajemne relacje** przycisk po utworzeniu pierwszej pary podmiotu prawnego. Po utworzeniu wzajemnego parę informacji dla firmy docelowej, jest kopiowany na firmę źródłową i na odwrót. Pozostanie dziennika zdefiniowane dla firmy docelowej. Większość organizacji Użyj tej samej konwencji nazewnictwa dla ich nazwy arkusza, tak aby nazwa arkusza jest taka sama. Jeśli nazwa arkusza jest inna, na polu, aby poinformować, że arkusz nie istnieje i może być wybrany inny arkusz pojawi się ostrzeżenie.


