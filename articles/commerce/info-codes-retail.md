---
title: Kody informacji i grupy kodów informacji
description: Ten artykuł zawiera omówienie kodów informacji i grup kodów informacji oraz sposobów ich używania.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.industry: Retail
ms.search.form: RetailInfocodeTable
ms.openlocfilehash: a6fc84db368c602f74778eb0a44ac52798dc5161
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273511"
---
# <a name="info-codes-and-info-code-groups"></a>Kody informacji i grupy kodów informacji

[!include [banner](includes/banner.md)]

Ten artykuł zawiera omówienie kodów informacji i grup kodów informacji oraz sposobów ich używania.

Kody informacji umożliwiają przechwytywanie danych w kasie punktu sprzedaży (POS). Kodów informacji można użyć do ponaglenia kasjera, aby wprowadzał informacje podczas różnych działań w punkcie sprzedaży, takich jak sprzedaż towaru, zwrot towaru lub wybieranie odbiorców. Kasjerzy mogą wybrać dane z listy lub wprowadzić je jako kod, liczbę, datę lub tekst. Powiadomienia można przypisywać do wstępnie zdefiniowanych akcji wykonywanych w sklepie, towarów detalicznych, metod płatności, odbiorców lub określonych działań wykonywanych w punkcie sprzedaży. Kodów informacji można użyć do wykonania następujących czynności:

- Rejestrowania dodatkowych informacji w czasie wykonywania transakcji, takich jak numer lotu lub przyczyna zwrotu;
- Monitowania kasjera o konieczności wyboru ceny dla poszczególnych produktów z listy cen.
- Łączenia z powiadomieniami kodu podrzędnego monitującego kasjera o podanie danych podczas wykonywania określonej akcji. Na przykład gdy klient zwraca produkt, można przypomnieć kasjerowi, aby zapytał o przyczyny zwrotu produktu. Kody podrzędne służą też do wyświetlania listy przyczyn, które kasjer może wybrać z listy.
- Sprzedaż produktu w ramach zwykłej sprzedaży, sprzedaży z rabatem lub oferowania bezpłatnych produktów.
- Pozwala monitować kasjera, aby wprowadzał wartość lub wybierał pozycje z listy kodów podrzędnych przy otwieraniu szuflady kasy bez wykonywania operacji sprzedaży.

## <a name="info-codes-group"></a>Grupa kodów informacji

W Commerce można utworzyć grupy kodów informacji. Grupy kodów informacji zapewniają większą elastyczność, umożliwiając definiowanie mniejszej ilości kodów informacji i używanie ich w bardziej zróżnicowany sposób. Grup kodów informacji można użyć w następujący sposób:

- Zdefiniuj mniejszą ilość kodów i ponowne je wykorzystuj w łatwy sposób. Kody informacji, które są uwzględnione w grupach kodów informacji nie mają wstępnie zdefiniowanych powiązań z innymi kodami informacji. Można dołączyć ten sam kod informacji do wielu grup kodów informacji, a następnie użyć priorytetów dotyczących kolejności wybierania w zależności od sytuacji.
- Połącz kody informacji z innymi kodami informacji lub grupami kodów informacji w celu zbierania informacji na temat produktu lub transakcji bez konieczności definiowania osobnego kodu informacji lub łączenia kodu informacji dla każdego scenariusza.

## <a name="info-code-examples"></a>Przykłady kodów informacji

**Przykład 1: Użyj ponownie kodów informacji**

Można połączyć kody informacji tak, aby po uruchomieniu jednego kodu informacji, natychmiast został uruchamiany inny kod informacji. Na przykład w przypadku sprzedaży niektórych produktów kasjer może być monitowany o zapytanie klienta, czy życzy sobie zakupić baterie i gwarancje dla produktu. Przy sprzedaży innych produktów kasjer może być monitowany o zapytanie klienta, czy życzy sobie zakupić baterie i poproszenie o podanie kodu pocztowego. Jeśli utworzymy połączone kody informacji dla tych scenariuszy, musimy skonfigurować każdą odmianę kodu informacji, dzięki czemu kasjer po odczytaniu monitu poprosi odbiorcę o odpowiednie informacje. Jeśli używamy grup kodów informacji, wspólne kody informacji, takie jak pytania o baterie, mogą być ustawione jeden raz, a następnie i wykorzystywane ponownie w wielu grupach kodów informacji. Można także użyć priorytetów w grupach kodów informacji do określania kolejności wyświetlania monitów.

**Przykład 2: Podłącz kody informacji do grup kodów informacji**

W przypadku sprzedaży niektórych produktów, na przykład przenośnych urządzeń, zawsze chcemy zbierać określone informacje, takich jak numer telefonu, identyfikator urządzenia przenośnego (MEID) i numer seryjny. Chcemy jednak gromadzić też i inne informacje w przypadku komputera typu tablet niż w przypadku telefonu komórkowego. Można skonfigurować grupę kodów informacji zawierającą monity o numer telefonu, numer seryjny i MEID, a następnie dołączyć grupę kodów informacji do indywidualnego kodu informacji. Po uruchomieniu kodu informacji dla określonego produktu można uruchomić grupę kodów informacji, co ułatwi zbieranie danych wspólnych bez konieczności definiowania wielu zestawów połączonych kodów informacji dla każdego urządzenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
