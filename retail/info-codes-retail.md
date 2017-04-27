---
title: Kody informacji
description: "Ten artykuł zawiera omówienie kodów informacji i grup kodów informacji oraz sposobów ich używania."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: sijoshi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d463d4ac9b4258c2282dc70547145ce38e4e8e98
ms.lasthandoff: 03/31/2017


---

# <a name="info-codes"></a>Kody informacji

[!include[banner](includes/banner.md)]


Ten artykuł zawiera omówienie kodów informacji i grup kodów informacji oraz sposobów ich używania.

Kody informacji umożliwiają przechwytywanie danych w kasie punktu sprzedaży (POS). Kodów informacji można użyć do ponaglenia kasjera, aby wprowadzał informacje podczas różnych działań w punkcie sprzedaży, takich jak sprzedaż towaru, zwrot towaru lub wybieranie odbiorców. Kasjerzy mogą wybrać dane z listy lub wprowadzić je jako kod, liczbę, datę lub tekst. Powiadomienia można przypisywać do wstępnie zdefiniowanych akcji wykonywanych w sklepie, towarów detalicznych, metod płatności, odbiorców lub określonych działań wykonywanych w punkcie sprzedaży. Kodów informacji można użyć do wykonania następujących czynności:
-   Rejestrowania dodatkowych informacji w czasie wykonywania transakcji, takich jak numer lotu lub przyczyna zwrotu;
-   Monitowania kasjera o konieczności wyboru ceny dla poszczególnych produktów z listy cen.
-   Łączenia z powiadomieniami kodu podrzędnego monitującego kasjera o podanie danych podczas wykonywania określonej akcji. Na przykład gdy klient zwraca produkt, można przypomnieć kasjerowi, aby zapytał o przyczyny zwrotu produktu. Kody podrzędne służą też do wyświetlania listy przyczyn, które kasjer może wybrać z listy.
-   Sprzedaż produktu w ramach zwykłej sprzedaży, sprzedaży z rabatem lub oferowania bezpłatnych produktów.
-   Pozwala monitować kasjera, aby wprowadzał wartość lub wybierał pozycje z listy kodów podrzędnych przy otwieraniu szuflady kasy bez wykonywania operacji sprzedaży.

## <a name="info-codes-group-in-retail-and-commerce"></a>Grupa kodów informacji w module Handel detaliczny i inny
W programie Dynamics 365 for Operations — Handel detaliczny można utworzyć grupy kodów informacji. Grupy kodów informacji zapewniają większą elastyczność, umożliwiając definiowanie mniejszej ilości kodów informacji i używanie ich w bardziej zróżnicowany sposób. Grup kodów informacji można użyć w następujący sposób:
-   Zdefiniuj mniejszą ilość kodów i ponowne je wykorzystuj w łatwy sposób. Kody informacji, które są uwzględnione w grupach kodów informacji nie mają wstępnie zdefiniowanych powiązań z innymi kodami informacji. Można dołączyć ten sam kod informacji do wielu grup kodów informacji, a następnie użyć priorytetów dotyczących kolejności wybierania w zależności od sytuacji.
-   Połącz kody informacji z innymi kodami informacji lub grupami kodów informacji w celu zbierania informacji na temat produktu lub transakcji bez konieczności definiowania osobnego kodu informacji lub łączenia kodu informacji dla każdego scenariusza.

## <a name="info-code-examples"></a>Przykłady kodów informacji
**Przykład 1: Użyj ponownie kodów informacji** W przypadku wcześniejszych wersji systemu , można połączyć kody informacji tak, aby po uruchomieniu jednego kodu informacji, natychmiast został uruchamiany inny kod informacji. Na przykład w przypadku sprzedaży niektórych produktów kasjer może być monitowany o zapytanie klienta, czy życzy sobie zakupić baterie i gwarancje dla produktu. Przy sprzedaży innych produktów kasjer może być monitowany o zapytanie klienta, czy życzy sobie zakupić baterie i poproszenie o podanie kodu pocztowego. Jeśli utworzymy połączone kody informacji dla tych scenariuszy, musimy skonfigurować każdą odmianę kodu informacji, dzięki czemu kasjer po odczytaniu monitu poprosi odbiorcę o odpowiednie informacje. Jeśli używamy grup kodów informacji, wspólne kody informacji, takie jak pytania o baterie, mogą być ustawione jeden raz, a następnie i wykorzystywane ponownie w wielu grupach kodów informacji. Można także użyć priorytetów w grupach kodów informacji do określania kolejności wyświetlania monitów. **Przykład 2: Podłącz kody informacji do grup kodów informacji** W przypadku sprzedaży niektórych produktów, na przykład przenośnych urządzeń, zawsze chcemy zbierać informacje, takich jak numer telefonu, identyfikator urządzenia przenośnego (MEID) i numer seryjny. Chcemy jednak gromadzić też i inne informacje w przypadku komputera typu tablet niż w przypadku telefonu komórkowego. Można skonfigurować grupę kodów informacji zawierającą monity o numer telefonu, numer seryjny i MEID, a następnie dołączyć grupę kodów informacji do indywidualnego kodu informacji. Po uruchomieniu kodu informacji dla określonego produktu można uruchomić grupę kodów informacji, co ułatwi zbieranie danych wspólnych bez konieczności definiowania wielu zestawów połączonych kodów informacji dla każdego urządzenia.

 
-






