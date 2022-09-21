---
title: Rabaty oparte na metodach płatności
description: Ten artykuł opisuje funkcję rabatu opartego na formie płatności, która umożliwia detalistom konfigurowanie rabatów dla konkretnych typów form płatności w Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: b11145c0c12f973b437ebf87921a5686d217d327
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473829"
---
# <a name="tender-based-discount"></a>Rabat oparty na formie płatności

[!include [banner](includes/banner.md)]

Ten artykuł opisuje funkcję rabatu opartego na formie płatności, która umożliwia detalistom konfigurowanie rabatów dla konkretnych typów form płatności w Microsoft Dynamics 365 Commerce.

Jest to typowa praktyka między detalistami wypuszczania prywatnych, markowych kart kredytowych. Detaliści korzystają z tego, że uzyskują preferowane stawki od banków. Ponadto, ponieważ karty te mogą zachęcić odbiorców do częstego odwiedzania sklepu i poprawienia wyników sprzedawców detalicznych. W związku z tym detaliści mają zachętę do zwiększania użycia przez klientów marki swoich firmowych kart kredytowych. Aby osiągnąć ten cel, często zapewniają dodatkowe rabaty dla klientów, którzy korzystają z tych kart kredytowych.

Sprzedawcy, którzy nie dostarczają markowych kart kredytowych, mogą zachęcać odbiorców do regulowania płatności za pomocą innych typów metod płatności, takich jak gotówka, karty upominkowe czy punkty lojalnościowe. Dzięki temu można zmniejszyć koszty opłat za przetwarzanie płatności z kart kredytowych. W związku z tym detaliści mogą oferować rabaty dla klientów, którzy korzystają z tych alternatywnych typów metod płatności.

## <a name="tender-based-discount"></a>Rabat oparty na formie płatności

Handel obsługuje *rabat oparty na formie płatności*, który sprzedawcy detaliczni konfigurują procent rabatu stosowany do transakcji, jeśli suma transakcji przekracza określoną kwotę, a odbiorca płaci przy użyciu preferowanego typu płatności. Rabat oparty na formie płatności jest oparty na warstwie, dzięki czemu różne wartości procentowe rabatu mogą być skojarzone z różnymi progami kwot. Klient może zdecydować, czy ma zostać wykonana płatność częściowa czy pełna płatność, a odpowiednia kwota rabatu jest ustalana w aparacie cen. Rabat oparty na formie płatności jest zawsze podawany w kwocie przed opodatkowaniem wierszy sprzedaży.

Rabat oparty na formie płatności może być zastosowany tylko do wierszy sprzedaży, w których ceny nie są zablokowane i są rozdzielane proporcjonalnie do wierszy kwalifikowanych. Jeśli do zamówienia dodawane są nowe wiersze sprzedaży, rabat oparty na metodzie płatności jest stosowany do nowych wierszy sprzedaży tylko podczas płatności. Podczas umieszczania zamówienia odbiorcy na potrzeby dostawy rabat oparty na metodzie płatności jest stosowany tylko do kwoty depozytu. Po złożeniu zamówienia, w trakcie realizacji ceny wierszy sprzedaży są zablokowane. Nie stosuje się rabatów opartych na metodach płatności do żadnego salda zastosowanego podczas odbioru lub autoryzowanego w trakcie wysyłki. Rabat oparty na metodach płatności może zostać zastosowany do całej kwoty zamówienia odbiorcy tylko wtedy, gdy sprzedawca połączy całą kwotę jako depozyt w czasie, gdy zamówienie jest składane.

Rabaty oparte na formie płatności nie pasują do rabatów opartych na towarach, takich jak proste rabaty, rabaty ilościowe, rabaty progowe, rabaty łączone i rabaty ręczne. Rabaty oparte na formach płatności są zawsze złożone w rabatach opartych na towarach. W związku z tym nawet jeśli do towaru zostanie zastosowany wyłączny rabat, rabat oparty na metodzie płatności jest nadal stosowany na zasadzie wyłącznego rabatu. Podobnie, jeśli do transakcji jest stosowany rabat progowy, a rabat na podstawie metody płatności zmniejsza sumę poniżej progu, rabat progowy jest nadal stosowany do transakcji.

Chociaż rabaty oparte na metodach płatności zmniejszają sumę częściową transakcji, to nie wpływa na automatyczne opłaty stosowane do transakcji. Na przykład, jeśli opłaty za dostawę są obliczane jako $5, ponieważ suma częściowa była większa niż $100, a rabat na podstawie metody płatności zmniejsza kwotę w taki sposób, że jest ona mniejsza niż $100, opłaty za dostawę pozostają $5 dla zamówienia.

W przypadku rabatów opartych na formie płatności są obecnie ograniczone do dwóch typów płatności: karty kredytowe i gotówka. Jeśli dla typu metody płatności skonfigurowano wiele rabatów opartych na typie płatności, stosowany jest tylko najlepszy rabat oparty na metodzie płatności.

## <a name="pos-user-experience"></a>Doświadczenia użytkownika w POS

Jeśli dla gotówki ustawiono rabat oparty na metodach płatności, a kasjer w punkcie sprzedaży (POS) wybierze przycisk **Płać gotówką**, by wyewidencjonować transakcję kasową i przeniesienia, rabat na podstawie formy płatności jest automatycznie stosowany dla transakcji. Zmniejszona kwota jest następnie wyświetlana jako saldo. Jeśli jednak Kasjer wybierze przycisk **Wstecz** na ekranie płatność, rabat zostanie usunięty, a kwota oryginalna zostanie wyświetlona na ekranie transakcji. Rabat na podstawie metody płatności jest usuwany, jeśli wiersz płatności jest unieważniony.

W przypadku płatności kartą kredytową detaliści mogą ustawiać rabat oparty na metodzie płatności dla jednego lub kilku typów kart kredytowych. Jednak system nie może sprawdzić typu karty kredytowej, która jest używana, jeśli karta nie zostanie autoryzowana. Jeśli rabat jest stosowany po autoryzacji, autoryzacja płatności będzie dotyczyła większej kwoty, ale przechwycenie płatności będzie dotyczyło mniejszej kwoty. Aby zapobiec takiej sytuacji, jeśli klient płaci za pomocą karty kredytowej, kasjer widzi okno dialogowe, w którym jest wyświetlana jakakolwiek preferowana karta kredytowa, które nada klientowi dodatkowy rabat. Kasjer może następnie zapytać, czy klient chce skorzystać z jednej z preferowanych kart w celu uzyskania dodatkowego rabatu. Jeśli kasjer wybiera kartę preferowaną, rabat na podstawie metody płatności jest stosowany do transakcji, a zmniejszona kwota jest wyświetlana na ekranie płatności. Autoryzacja będzie dotyczyć zmniejszonej kwoty. Jeśli klient użyje karty, która różni się od karty wybranej przez kasjera, wyświetlany jest komunikat o błędzie, a autoryzacja jest unieważniona.

## <a name="call-center-user-experience"></a>Doświadczenie użytkownika biura obsługi

Gdy użytkownik biura obsługi wybierze opcję **Zakończ** w ramach zlecenia biura obsługi, wyświetlane jest **Sumy**. Najpierw sumy na tym ekranie nie zawierają rabatów opartych na metodzie płatności, ponieważ metoda płatności nie została jeszcze wybrana. Na ekranie **Dodaj płatność**, jeśli użytkownik wybierze metodę płatności, dla której jest skonfigurowany rabat oparty na metodzie płatności, kwota płatności zostanie automatycznie skorygowana, tak aby odzwierciedlała zdyskontowaną kwotę. Podobnie jak klient w punkcie sprzedaży, klient biura obsługi może zdecydować, czy zapłacić pełną płatność, czy częściową płatność. Na podstawie zastosowanej kwoty rabat na podstawie metody płatności jest stosowany w zamówieniu sprzedaży.

> [!NOTE]
> Nie wykonuje się weryfikacji karty dla zamówień z rozmów telefonicznych. Jeśli na przykład użytkownik biura obsługi wybiera kartę Visa jako kartę kredytową, ale klient używa karty Mastercard, system nadal stosuje rabat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
