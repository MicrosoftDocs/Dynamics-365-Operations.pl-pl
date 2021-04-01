---
title: Rabaty oparte na metodach płatności
description: Ten temat stanowi przegląd funkcji, które umożliwiają detalistom konfigurowanie rabatów dla konkretnych typów metod płatności.
author: bebeale
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 98631d8f9fb2c05621f69fa67c9b60472198ee6b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232574"
---
# <a name="tender-based-discounts"></a>Rabaty oparte na metodach płatności

[!include [banner](includes/banner.md)]


Jest to typowa praktyka między detalistami wypuszczania prywatnych, markowych kart kredytowych. Detaliści korzystają z tego, że uzyskują preferowane stawki od banków. Ponadto, ponieważ karty te mogą zachęcić odbiorców do częstego odwiedzania sklepu i poprawienia wyników sprzedawców detalicznych. W związku z tym detaliści mają zachętę do zwiększania użycia przez klientów marki swoich firmowych kart kredytowych. Aby osiągnąć ten cel, często zapewniają dodatkowe rabaty dla klientów, którzy korzystają z tych kart kredytowych.

Sprzedawcy, którzy nie dostarczają markowych kart kredytowych, mogą zachęcać odbiorców do regulowania płatności za pomocą innych typów metod płatności, takich jak gotówka, karty upominkowe czy punkty lojalnościowe. Dzięki temu można zmniejszyć koszty opłat za przetwarzanie płatności z kart kredytowych. W związku z tym detaliści mogą oferować rabaty dla klientów, którzy korzystają z tych alternatywnych typów metod płatności.

W Microsoft Dynamics 365 Commerce detaliści mogą skonfigurować procent rabatu stosowany do kwalifikowanych wierszy, jeśli odbiorca płaci za pomocą preferowanego typu metody płatności. Klient może zdecydować, czy ma zostać wykonana płatność częściowa czy pełna płatność, a odpowiednia kwota rabatu jest ustalana w Commerce. Należy zwrócić uwagę, że rabat jest zawsze podawany na kwotę przed opodatkowaniem z kwalifikujących się towarów.

Rabaty oparte na metodach płatności nie konkurują z rabatami opartymi na pozycjach, np. rabatami okresowymi lub ręcznymi. Są one zawsze składane w ramach rabatów dla towarów. W związku z tym nawet jeśli do towaru zostanie zastosowany wyłączny rabat okresowy, rabat oparty na metodzie płatności jest nadal stosowany na zasadzie wyłącznego rabatu okresowego. Podobnie, jeśli do transakcji jest stosowany rabat progowy, a rabat na podstawie metody płatności zmniejsza sumę poniżej progu, rabat progowy jest nadal stosowany do transakcji.

Chociaż rabaty oparte na metodach płatności zmniejszają sumę częściową transakcji, to nie wpływa na automatyczne opłaty stosowane do transakcji. Na przykład, jeśli opłaty za dostawę są obliczane jako $5, ponieważ suma częściowa była większa niż $100, a rabat na podstawie metody płatności zmniejsza kwotę w taki sposób, że jest ona mniejsza niż $100, opłaty za dostawę są nadal $5 dla zamówienia.


> [!NOTE]
> Rabaty oparte na metodach płatności są rozdzielane proporcjonalnie do wierszy sprzedaży kwalifikowanej i zmniejszają kwotę przed opodatkowaniem poszczególnych wierszy. Jeśli dla typu metody płatności skonfigurowano wiele rabatów opartych na metodach płatności (np. gotówka), stosowany jest tylko najlepszy rabat oparty na metodzie płatności.

Rabaty oparte na metodach płatności mogą być stosowane tylko do wierszy sprzedaży, w których ceny nie są zablokowane. Jeśli do zamówienia dodawane są nowe wiersze sprzedaży, rabat oparty na metodzie płatności jest stosowany do nowych wierszy sprzedaży tylko podczas płatności. Podczas umieszczania zamówienia odbiorcy na potrzeby pobrania lub wysyłki rabat oparty na metodzie płatności jest stosowany tylko do kwoty depozytu. Po złożeniu zamówienia, w trakcie realizacji ceny wierszy sprzedaży są zablokowane. Dlatego nie stosuje się rabatów opartych na metodach płatności do żadnego salda zastosowanego podczas odbioru lub autoryzowanego w trakcie wysyłki. Rabat oparty na metodach płatności może zostać zastosowany do całej kwoty zamówienia odbiorcy tylko wtedy, gdy sprzedawca połączy całą kwotę jako depozyt w czasie, gdy zamówienie jest składane.

> [!IMPORTANT]
> W przypadku rabatów opartych na metodach płatności w Commerce są obecnie ograniczone do dwóch typów płatności: karty kredytowe i gotówka.

## <a name="pos-user-experience"></a>Doświadczenia użytkownika w POS

Jeśli dla gotówki ustawiono rabat oparty na metodach płatności, a kasjer w punkcie sprzedaży (POS) wybierze przycisk, który jest mapowany na operację płatności gotówkowej, rabat na podstawie metody płatności jest automatycznie stosowany dla transakcji. Zmniejszona kwota jest następnie wyświetlana jako saldo. Jeśli jednak Kasjer wybierze przycisk **Wstecz** na ekranie płatność, rabat zostanie usunięty, a kwota oryginalna zostanie wyświetlona na ekranie transakcji. Rabat na podstawie metody płatności jest usuwany, jeśli wiersz płatności jest unieważniony.

W przypadku płatności kartą detaliści mogą ustawiać rabat oparty na metodzie płatności dla jednego lub kilku typów kart kredytowych. Jednak system nie może sprawdzić typu karty kredytowej, która jest używana, jeśli karta nie zostanie autoryzowana. Jeśli rabat jest stosowany po autoryzacji, autoryzacja płatności będzie dotyczyła większej kwoty, ale przechwycenie płatności będzie dotyczyło mniejszej kwoty.

Aby zapobiec takiej sytuacji, jeśli klient płaci za pomocą karty kredytowej, kasjer widzi okno dialogowe, w którym jest wyświetlana lista kart kredytowych, które nadadzą klientowi dodatkowe oszczędności. Kasjer może następnie zapytać, czy klient chce skorzystać z jednej z preferowanych kart w celu uzyskania dodatkowego rabatu. Jeśli kasjer używa karty preferowanej, rabat na podstawie metody płatności jest stosowany do transakcji, a zmniejszona kwota jest wyświetlana na ekranie płatności. Autoryzacja będzie dotyczyć zmniejszonej kwoty. Jeśli klient użyje karty, która różni się od karty wybranej przez kasjera, wyświetlany jest komunikat o błędzie, a autoryzacja jest unieważniona.


## <a name="call-center-user-experience"></a>Doświadczenie użytkownika biura obsługi

Gdy użytkownik wybierze opcję **Zakończ** w ramach zlecenia biura obsługi, wyświetlany jest ekran **Sumy**. Najpierw sumy na tym ekranie nie zawierają rabatów opartych na metodzie płatności, ponieważ metoda płatności nie została jeszcze wybrana. Na ekranie **Dodaj płatność**, jeśli użytkownik wybierze metodę płatności, dla której jest skonfigurowany rabat oparty na metodzie płatności, kwota płatności zostanie automatycznie skorygowana, tak aby odzwierciedlała zdyskontowaną kwotę. Podobnie jak klient w punkcie sprzedaży, klient biura obsługi może zdecydować, czy zapłacić pełną płatność, czy częściową płatność. Na podstawie zastosowanej kwoty rabat na podstawie metody płatności jest stosowany w zamówieniu sprzedaży.

> [!NOTE]
> Nie wykonuje się weryfikacji karty dla zamówień z rozmów telefonicznych. Jeśli na przykład użytkownik biura obsługi wybiera kartę Visa jako kartę kredytową, ale klient używa karty Mastercard, system nadal stosuje rabat.

## <a name="exclude-items-from-discounts"></a>Wyklucz pozycje z rabatów

Detaliści często wykluczają niektóre produkty, takie jak nowe towary lub pozycje pożądane, z rabatów Jednak nadal mogą być stosowane rabaty oparte na metodach płatności. Na przykład detalista konfiguruje moduł Commerce w taki sposób, aby nie zezwalał na rabaty na pozycje ani rabaty ręczne. Jeśli jednak klient płaci za pomocą preferowanej metody płatności, rabaty oparte na metodzie płatności będą stosowane w Commerce. Aby w ten sposób skonfigurować Commerce, detaliści muszą przejść do obszaru **Zarządzanie informacjami o produktach > Produkty> Zwolnione produkty**, wybrać towar, a następnie w na skróconej karcie **Commerce** ustawić opcje **Nie zezwalaj na żadne rabaty** i nie **Nie zezwalaj na rabaty oparte na metodach płatności** na wartość **Nie**, a w opcjach **Nie zezwalaj na rabaty** i **Nie zezwalaj na rabaty ręczne** ustawić wartość **Tak**.

> [!NOTE]
> Jeśli konfiguracja **Nie zezwalaj na żadne rabaty** jest ustawiona wartość **Tak**, do produktu nie będą stosowane żadne rabaty. Nie będą nawet stosowane rabaty oparte na metodach płatności.


[!INCLUDE[footer-include](../includes/footer-banner.md)]