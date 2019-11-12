---
title: Rabaty oparte na metodach płatności
description: Ten temat stanowi przegląd funkcji, które umożliwiają detalistom konfigurowanie rabatów dla konkretnych typów metod płatności.
author: bebeale
manager: AnnBe
ms.date: 10/25/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 245ee647a3b86303df046fda5bba406c7a2485b5
ms.sourcegitcommit: b0c176d5d24939307c6d0a6dbe7656007ca53710
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "2673572"
---
# <a name="tender-based-discounts"></a>Rabaty oparte na metodach płatności

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Jest to typowa praktyka między detalistami wypuszczania prywatnych, markowych kart kredytowych. Detaliści korzystają z tego, że uzyskują preferowane stawki od banków. Ponadto, ponieważ karty te mogą zachęcić odbiorców do częstego odwiedzania sklepu i poprawienia wyników sprzedawców detalicznych. W związku z tym detaliści mają zachętę do zwiększania użycia przez klientów marki swoich firmowych kart kredytowych. Aby osiągnąć ten cel, często zapewniają dodatkowe rabaty dla klientów, którzy korzystają z tych kart kredytowych.

Sprzedawcy, którzy nie dostarczają markowych kart kredytowych, mogą zachęcać odbiorców do regulowania płatności za pomocą innych typów metod płatności, takich jak gotówka, karty upominkowe czy punkty lojalnościowe. Dzięki temu można zmniejszyć koszty opłat za przetwarzanie płatności z kart kredytowych. W związku z tym detaliści mogą oferować rabaty dla klientów, którzy korzystają z tych alternatywnych typów metod płatności.

W Microsoft Dynamics 365 Retail detaliści mogą skonfigurować procent rabatu stosowany do kwalifikowanych wierszy, jeśli odbiorca płaci za pomocą preferowanego typu metody płatności Klient może zdecydować, czy ma zostać wykonana płatność częściowa czy pełna płatność, a odpowiednia kwota rabatu jest ustalana w Retail. Należy zwrócić uwagę, że rabat jest zawsze podawany na kwotę przed opodatkowaniem z kwalifikujących się towarów.

Rabaty oparte na metodach płatności nie konkurują z rabatami opartymi na pozycjach, np. rabatami okresowymi lub ręcznymi. Są one zawsze składane w ramach rabatów dla towarów. W związku z tym nawet jeśli do towaru zostanie zastosowany wyłączny rabat okresowy, rabat oparty na metodzie płatności jest nadal stosowany na zasadzie wyłącznego rabatu okresowego. Podobnie, jeśli do transakcji jest stosowany rabat progowy, a rabat na podstawie metody płatności zmniejsza sumę poniżej progu, rabat progowy jest nadal stosowany do transakcji.

Chociaż rabaty oparte na metodach płatności zmniejszają sumę częściową transakcji, to nie wpływa na automatyczne opłaty stosowane do transakcji. Na przykład, jeśli opłaty za dostawę są obliczane jako $5, ponieważ suma częściowa była większa niż $100, a rabat na podstawie metody płatności zmniejsza kwotę w taki sposób, że jest ona mniejsza niż $100, opłaty za dostawę są nadal $5 dla zamówienia.

> [!NOTE]
> Rabaty oparte na metodach płatności są rozdzielane proporcjonalnie do wierszy sprzedaży kwalifikowanej i zmniejszają kwotę przed opodatkowaniem poszczególnych wierszy. Jeśli dla typu metody płatności skonfigurowano wiele rabatów opartych na metodach płatności (np. gotówka), stosowany jest tylko najlepszy rabat oparty na metodzie płatności.

Rabaty oparte na metodach płatności mogą być stosowane tylko do wierszy sprzedaży, w których ceny nie są zablokowane. Jeśli do zamówienia dodawane są nowe wiersze sprzedaży, rabat oparty na metodzie płatności jest stosowany do nowych wierszy sprzedaży tylko podczas płatności. Podczas umieszczania zamówienia odbiorcy na potrzeby pobrania lub wysyłki rabat oparty na metodzie płatności jest stosowany tylko do kwoty depozytu. Po złożeniu zamówienia, w trakcie realizacji ceny wierszy sprzedaży są zablokowane. Dlatego nie stosuje się rabatów opartych na metodach płatności do żadnego salda zastosowanego podczas odbioru lub autoryzowanego w trakcie wysyłki. Rabat oparty na metodach płatności może zostać zastosowany do całej kwoty zamówienia odbiorcy tylko wtedy, gdy sprzedawca połączy całą kwotę jako depozyt w czasie, gdy zamówienie jest składane.

> [!IMPORTANT]
> W przypadku rabatów opartych na metodach płatności w Retail są obecnie ograniczone do dwóch typów płatności: karty kredytowe i gotówka.

## <a name="pos-user-experience"></a>Doświadczenia użytkownika w POS

Jeśli dla gotówki ustawiono rabat oparty na metodach płatności, a kasjer w punkcie sprzedaży (POS) wybierze przycisk, który jest mapowany na operację płatności gotówkowej, rabat na podstawie metody płatności jest automatycznie stosowany dla transakcji. Zmniejszona kwota jest następnie wyświetlana jako saldo. Jeśli jednak Kasjer wybierze przycisk **Wstecz** na ekranie płatność, rabat zostanie usunięty, a kwota oryginalna zostanie wyświetlona na ekranie transakcji. Rabat na podstawie metody płatności jest usuwany, jeśli wiersz płatności jest unieważniony.

W przypadku płatności kartą detaliści mogą ustawiać rabat oparty na metodzie płatności dla jednego lub kilku typów kart kredytowych. Jednak system nie może sprawdzić typu karty kredytowej, która jest używana, jeśli karta nie zostanie autoryzowana. Jeśli rabat jest stosowany po autoryzacji, autoryzacja płatności będzie dotyczyła większej kwoty, ale przechwycenie płatności będzie dotyczyło mniejszej kwoty.

Aby zapobiec takiej sytuacji, jeśli klient płaci za pomocą karty kredytowej, kasjer widzi okno dialogowe, w którym jest wyświetlana lista kart kredytowych, które nadadzą klientowi dodatkowe oszczędności. Kasjer może następnie zapytać, czy klient chce skorzystać z jednej z preferowanych kart w celu uzyskania dodatkowego rabatu. Jeśli kasjer używa karty preferowanej, rabat na podstawie metody płatności jest stosowany do transakcji, a zmniejszona kwota jest wyświetlana na ekranie płatności. Autoryzacja będzie dotyczyć zmniejszonej kwoty. Jeśli klient użyje karty, która różni się od karty wybranej przez kasjera, wyświetlany jest komunikat o błędzie, a autoryzacja jest unieważniona.

## <a name="call-center-user-experience"></a>Doświadczenie użytkownika biura obsługi

Gdy użytkownik wybierze opcję **Zakończ** w ramach zlecenia biura obsługi, wyświetlany jest ekran **Sumy**. Najpierw sumy na tym ekranie nie zawierają rabatów opartych na metodzie płatności, ponieważ metoda płatności nie została jeszcze wybrana. Na ekranie **Dodaj płatność**, jeśli użytkownik wybierze metodę płatności, dla której jest skonfigurowany rabat oparty na metodzie płatności, kwota płatności zostanie automatycznie skorygowana, tak aby odzwierciedlała zdyskontowaną kwotę. Podobnie jak klient w punkcie sprzedaży, klient biura obsługi może zdecydować, czy zapłacić pełną płatność, czy częściową płatność. Na podstawie zastosowanej kwoty rabat na podstawie metody płatności jest stosowany w zamówieniu sprzedaży.

> [!NOTE]
> Nie wykonuje się weryfikacji karty dla zamówień z rozmów telefonicznych. Jeśli na przykład użytkownik biura obsługi wybiera kartę Visa jako kartę kredytową, ale klient używa karty Mastercard, system nadal stosuje rabat.

## <a name="exclude-items-from-discounts"></a>Wyklucz pozycje z rabatów

Detaliści często wykluczają niektóre produkty, takie jak nowe towary lub pozycje pożądane, z rabatów Jednak nadal mogą być stosowane rabaty oparte na metodach płatności. Na przykład detalista konfiguruje moduł Retail w taki sposób, aby nie zezwalał na rabaty na pozycje ani rabaty ręczne. Jeśli jednak klient płaci za pomocą preferowanej metody płatności, rabaty oparte na metodzie płatności będą stosowane w Retail. Aby w ten sposób skonfigurować Retail, detaliści muszą wyłączyć opcje **Nie zezwalaj na żadne rabaty** i **Nie zezwalaj na rabaty oparte na metodach płatności** oraz włączuć opcje **Nie zezwalaj na rabaty w sprzedaży detalicznej** i **Nie zezwalaj na rabaty ręczne**. Dostępne opcje znajdują się na stronie **Zwolnione produkty** na karcie **Detal**.

> [!NOTE]
> Jeśli jest włączona konfiguracja **Nie zezwalaj na żadne rabaty**, do produktu nie będą stosowane żadne rabaty. Nie będą nawet stosowane rabaty oparte na metodach płatności.
