---
title: Kalendarze, lata i okresy obrachunkowe
description: "W tym artykule omówiono narzędzia kalendarzy obrachunkowych, lat obrachunkowych i okresów oraz możliwości ich wykorzystywania dla firm, środków trwałych i budżetowania."
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 431d654aaffc27d54fd590dc7d5d2ab6c2313908
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="fiscal-calendars-fiscal-years-and-periods"></a>Kalendarze, lata i okresy obrachunkowe

[!include[banner](../includes/banner.md)]


W tym artykule omówiono narzędzia kalendarzy obrachunkowych, lat obrachunkowych i okresów oraz możliwości ich wykorzystywania dla firm, środków trwałych i budżetowania.

Kalendarze obrachunkowe zapewniają ramy dla działań finansowych organizacji. Każdy kalendarz obrachunkowy zawiera jedno lub więcej lat obrachunkowych, a każdy rok obrachunkowego posiada wiele okresów. Kalendarze obrachunkowe mogą być oparte na roku kalendarzowym od 1 stycznia do 31 grudnia lub na terminach, które można wybrać. Na przykład niektóre organizacje wybierają kalendarz obrachunkowy, który rozpoczyna się 1 lipca roku jednego roku i kończy się 30 czerwca kolejnego roku. 

Jest nieograniczona liczba kalendarzy obrachunkowych, które można utworzyć oraz nieograniczona liczba lat obrachunkowych, które mogą być tworzone dla kalendarza obrachunkowego. Każdy kalendarz obrachunkowy jest niezależny od organizacji i może być używany przez wiele firm w organizacji. Na przykład organizacja ma osiem działów, a każdy dział to osobna firma. Pięć z nich posiada ten sam kalendarz obrachunkowy, a trzy używają innych kalendarzy obrachunkowych. Można utworzyć jeden kalendarz obrachunkowy dla pięciu firm, które współużytkują ten sam kalendarz obrachunkowy, a następnie utworzyć osobne kalendarze obrachunkowe dla innych firm.

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>Tworzenie kalendarzy obrachunkowych, lat obrachunkowych i okresów
Na stronie Kalendarze obrachunkowe można tworzyć i usuwać kalendarze obrachunkowe, lata obrachunkowe i okresy. Można także podzielić istniejące okresy i tworzyć okresów zamknięcia, które mogą być używane do zamykania roku obrachunkowego. 

Okres zamknięcia jest używany do oddzielania transakcji księgi głównej, które są generowane po zamknięciu roku obrachunkowego. Gdy transakcje zamknięcia są w jednym okresie obrachunkowym, łatwiej jest tworzyć sprawozdania finansowe zawierające lub wyłączające różne typy wpisów zamknięcia. Jeśli rok obrachunkowy podzielony jest na 12 okresów obrachunkowych, okres zamknięcia jest zazwyczaj 13. okresem. Jednak okres zamknięcia można utworzyć od dowolnego okresu, który ma stan Otwarty. 

Podczas tworzenia okresu zamknięcia, należy wybrać okres o stanie Otwarty i posiadający daty, które mają być użyte. Nowy okres zamknięcia skopiuje daty rozpoczęcia i zakończenia z istniejącego okresu. Pierwotny okres będzie istniał w dalszym ciągu. Na przykład należy wybrać Okres 12, który jest ostatnim okresem w roku obrachunkowym, a jego daty to 1 sierpnia do 31 sierpnia. Należy wprowadzić nazwę dla okresu zamknięcia, na przykład Zamknięcie. Po utworzeniu nowego okresu zamknięcia, użytkownik ma teraz pierwotny okres i okres zamknięcia. Oba rozpoczynają się dniu 1 sierpnia, a kończą 31 sierpnia.

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>Wybieranie kalendarzy obrachunkowych dla ksiąg, środkami trwałymi i cyklów budżetu
Kalendarze obrachunkowe są używane z amortyzacją środków trwałych, transakcjami finansowymi i cyklami budżetu. Po utworzeniu kalendarza obrachunkowego, można go używać do obsługi wielu celów. Można wybrać kalendarz obrachunkowy dla modelu ewidencji lub księgi amortyzacji z myślą o kalendarzu środków trwałych. Można wybrać kalendarz obrachunkowy dla księgi z myślą o kalendarzu księgi. Ponadto można wybrać kalendarz obrachunkowy dla cyklu budżetu z myślą o kalendarzu budżetu. Dla wszystkich opcji można używać tego samego kalendarza obrachunkowego.

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>Wybierz kalendarz obrachunkowy dla danej firmy.

Formularz Księga umożliwia wybranie kalendarza obrachunkowego, który ma być używane dla księgi w firmie. Na stronie Księga należy wybrać kalendarz obrachunkowy dla każdej firmy. Po wybraniu kalendarza obrachunkowego, na stronie Kalendarz księgi można skonfigurować stany okresów i uprawnienia dla każdego z okresów, który jest częścią roku obrachunkowego.

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>Wybierz kalendarz obrachunkowy dla środków trwałych

Można wybrać kalendarz obrachunkowy dla modelu ewidencji lub księgi amortyzacji, tak że kalendarz obrachunkowy będzie używany przez środki trwałe korzystające z wybranego modelu ewidencjonowania lub księgi amortyzacji. Można wybrać dowolne kalendarze obrachunkowe zdefiniowane na stronie Kalendarze obrachunkowe.

### <a name="define-budget-cycle-time-spans"></a>Określanie okresów cyklu budżetu

Cykle budżetu to okres czasu, w którym używany jest budżet. Cykle budżetu mogą zawierać część roku obrachunkowego lub wielu lat obrachunkowych, takich jak cykl budżetu dwurocznego o długości dwóch lat lub trzyrocznego cyklu budżetu realizowanego przez trzy lata. Okres cyklu budżetu określa liczbę okresów, które są uwzględnione w cyklu budżetu. Aby zastosować okres cyklu budżetu, użyj strony Okresy cyklu budżetu.

## <a name="maintain-periods-for-your-organization"></a>Obsługa okresów dla organizacji
Można użyć strony Kalendarz księgi, aby wyświetlić szczegóły dla kalendarza obrachunkowego, lat obrachunkowych i okresów używanych przez organizację. Można także zmienić stan okresów i wybrać użytkowników, którzy mogą księgować transakcje rachunku kosztów dla okresów. Na przykład na początku nowego okresu możesz chcieć zakończyć księgowanie transakcji finansowych z poprzedniego okresu dla danej grupy użytkowników, natomiast dla innych grup, aby pracowały tylko w nowym okresie.






