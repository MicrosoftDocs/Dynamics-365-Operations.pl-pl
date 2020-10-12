---
title: Omówienie stron koszyka i realizacji zamówienia
description: Ten temat stanowi omówienie stron koszyka i realizacji transakcji w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e932be31a301ef5aacb68fa4e710d8a9137b7263
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817785"
---
# <a name="cart-and-checkout-pages-overview"></a>Omówienie stron koszyka i realizacji zamówienia

[!include [banner](includes/banner.md)]

Ten temat stanowi omówienie stron koszyka i realizacji transakcji w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Strona koszyka w witrynie e-Commerce zawiera wszystkie towary dodane przez odbiorcę do koszyka. Strona koszyka jest budowana przy użyciu modułu koszyka. Moduł koszyka jest kontenerem obsługującym wszystkie moduły wymagane do zaprezentowania towarów w koszyku. Moduł koszyk może również wykorzystywać inne moduły do wyświetlania podsumowania zamówień i kodów promocyjnych, które zostały zastosowane do zamówienia odbiorcy.

Strona realizacja klienta w witrynie e-Commerce zawiera przebieg procesu krok po kroku, co pozwala klientom na wprowadzenie wszystkich informacji wymaganych do zrealizowania zamówienia. Moduł realizacji transakcji może zawierać moduły obsługujące adres wysyłkowy, metody wysyłki, informacje bilingowe, podsumowanie zamówień oraz inne informacje związane z zamówieniami odbiorców.

## <a name="cart-page"></a>Strona koszyka

Strona koszyka służy jako torba do zakupów i zawiera wszystkie towary dodane do koszyka.

Poniższa ilustracja pokazuje przykład strony koszyka zbudowanej przy użyciu biblioteki modułów online i motywu „Fabrikam”.

![Przykład strony koszyka](./media/cart2.PNG)

Główna treść strony koszyka pokazuje wszystkie elementy, które klient dodał do koszyka. Zaprezentuj wszystkie odpowiednie rabaty. Rabaty te obejmują rabaty złożone. Przykładem mogą być „Kup 3 pozycje i uzyskaj 10% zniżki” lub „Kup butelkę i plecak, aby uzyskać 10% zniżki”. W module podsumowanie zamówień jest wyświetlana kwota należna po zastosowaniu rabatów, kosztów wysyłki, podatków itp. Istnieje także moduł kodu promocyjnego, który pozwala odbiorcy na zastosowanie lub usunięcie kodów promocyjnych.

Odbiorca może kupować anonimowo lub jako użytkownika zalogowanego. Jeśli odbiorca jest zalogowany, towary w koszyku są zachowywane między sesjami. Dzięki temu Klient może kontynuować zakupy z wielu urządzeń.

Z koszyka klient może kontynuować proces realizacji transakcji. Klient może inicjować realizację transakcji jako gość lub jako użytkownik zalogowany.

Aby uzyskać informacje dotyczące sposobu tworzenia strony koszyka, zapoznaj się z tematem [Dodawanie modułu koszyka do strony](add-cart-module.md).

## <a name="checkout-page"></a>Strona realizacji transakcji

Strona realizacja jest miejscem, w którym odbiorcy wprowadzają informacje wymagane do zrealizowania zamówienia.

Na poniższej ilustracji przedstawiono przykład strony realizacji, która została utworzona przy użyciu biblioteki modułów.

![Przykład strony realizacji](./media/Checkout.PNG)

Główną treścią strony realizacja jest to, gdzie są zbierane wszystkie informacje o zamówieniach. Informacje te obejmują adres wysyłkowy, opcje dostawy oraz informacje o płatności. Realizacja zamówienia ma przebieg krok po kroku, ponieważ informacje muszą zostać wprowadzone w określonym zamówieniu do przetworzenia. Na przykład adres wysyłkowy musi zostać wprowadzony, aby można było obliczyć koszty wysyłki, a płatność może być autoryzowana.

### <a name="shipping-address"></a>Adres wysyłkowy

Adres wysyłkowy jest wymagany, jeśli towary muszą zostać wysłane. Dla każdego ustawienia regionalnego można skonfigurować format adresów wysyłkowych Dynamics 365 Commerce. Jeśli na przykład towary zostaną wysłane do Stanów Zjednoczonych, adres wysyłkowy musi zawierać adres ulicy, stan i kod pocztowy. Niektóre podstawowe czynności sprawdzające dotyczą pól adresu wysyłkowego, takich jak sprawdzanie poprawności znaków alfanumerycznych, długość maksymalna oraz liczby. Chociaż ważność samego adresu nie jest weryfikowana, weryfikację można wykonać za pomocą dostosowanych usług innych firm.

Adres wysyłkowy jest stosowany do wszystkich towarów w koszyku, dla których wybrano opcję „wyślij”. W przypadku użycia przepływu realizacji dostępnego w trybie online biblioteki modułów, poszczególne towary w koszyku nie mogą być wysyłane pod różne adresy. Jeśli ta możliwość jest wymagana, można ją zaimplementować poprzez dostosowanie modułów realizacji transakcji.

Po podanym adresie wysyłkowym zostaną wyświetlone metody wysyłki dostępne w sklepie internetowym Dynamics 365 Commerce. Metody wysyłki i adresy, które obsługuje, mogą być konfigurowane w module Commerce.

### <a name="payment"></a>Płatność

Następnym krokiem w procesie realizacji jest płatność. W e-Commerce wiele metod płatności można używać do realizowania zamówień, takich jak karty kredytowe, karty upominkowe i punkty lojalnościowe. Można również użyć kombinacji tych metod płatności. W zależności od używanych metod płatności mogą być wymagane dodatkowe informacje. Na przykład płatność kartą kredytową wymaga adresu na fakturze. Płatności kartą kredytową są przetwarzane przy użyciu łącznika płatności Adyen.

#### <a name="loyalty-points"></a>Punkty lojalnościowe

Podczas procesu realizacji transakcji odbiorca, który jest członkiem programu lojalnościowego i który zbiera punkty lojalnościowe, może zrealizować te punkty lojalnościowe w zamówieniu. Moduł punkty lojalnościowe jest wyświetlany tylko wtedy, gdy odbiorca ma istniejące członkostwo w programie lojalnościowym. W przypadku użytkowników niebędących członkami systemu i gości ten moduł jest ukryty.

#### <a name="gift-cards"></a>Karty upominkowe

Biblioteka modułów umożliwia zrealizowanie wewnętrznych kart podarunkowych na zamówienie. Aby można było zastosować wewnętrzną kartę upominkową, odbiorca musi być zalogowany. W przypadku dodatkowych zabezpieczeń zalecane jest dostosowanie przepływu przy użyciu osobistego numeru identyfikacyjnego (PIN) dla wewnętrznych kart upominkowych.

### <a name="signed-in-and-guest-users"></a>Zalogowani użytkownicy i goście

Klient może ukończyć proces kasy jako użytkownik gość lub użytkownik zalogowany. Jeśli odbiorca zarejestruje się w systemie, automatycznie jest pobierana informacja o koncie, taka jak zapisane adresy wysyłkowe i zapisane szczegóły karty kredytowej.

### <a name="order-summary"></a>Podsumowanie zamówienia

W ramach procesu realizacji transakcji jest wyświetlane podsumowanie towarów wierszowych w koszyku, dzięki czemu odbiorca może zweryfikować zamówienie przed jego umieszczeniem. Nie można edytować towarów w wierszach w trakcie przepływu realizacji transakcji. Łącze do koszyka jest jednak dostarczane w sytuacji, gdy użytkownik chce wrócić i edytować pozycje w wierszu.

Gdy odbiorca poda informacje dotyczące wysyłki i rozliczania zamówienia, podsumowanie zamówień odzwierciedla kwotę należną po punktach lojalnościowych, kartami upominkowymi i innymi płatnościami.

### <a name="order-confirmation-and-email"></a>Potwierdzenie zamówienia i e-mail

Gdy odbiorca złoży zamówienie, dostarczany jest numer potwierdzenia. W tym momencie płatność została autoryzowana, ale nie została obciążona. Płatność zostanie naliczona tylko wtedy, gdy zamówienie zostanie zrealizowane (to znaczy, gdy jest wysyłana lub pobierana).

Po utworzeniu zamówienia do odbiorcy jest wysyłana wiadomość e-mail z potwierdzeniem zamówienia.

Aby uzyskać więcej informacji dotyczących sposobu tworzenia strony realizacji, zapoznaj się z tematem [Dodawanie modułu realizacji do strony](add-checkout-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie strony głównej](quick-tour-home-page.md)

[Omówienie stron szczegółów produktów](quick-tour-pdp.md)

[Omówienie stron zarządzania kontem](quick-tour-account-management.md)
