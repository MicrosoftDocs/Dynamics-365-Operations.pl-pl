---
title: Zaliczki w aplikacji Dynamics 365 Commerce
description: Ten artykuł zawiera omówienie przetwarzania transakcji przedpłaty w Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780365"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Zaliczki w aplikacji Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

Ten artykuł zawiera omówienie przetwarzania transakcji przedpłaty w Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce przetwarza transakcje przedpłat dla następujących typów płatności, które są używane w rozrachunkach z odbiorcami lub handlu:

- **Wpłata na konto odbiorcy** – Klient wpłaca kaucję w punkcie sprzedaży (POS). Commerce przetwarza płatność kaucji jako transakcję przedpłaty. Podczas księgowania transakcji tworzony jest dziennik płatności i księgowany na stronie **Karta dziennika** w Commerce headquarters. Pole wyboru **Załącznik arkusza przedpłat** na karcie **Płatność** jest automatycznie zaznaczone dla arkusza płatności. Aby uzyskać więcej informacji, w tym informacje dotyczące przedpłat i podatków, odpowiednie dla regionu docelowego, zobacz zawartość [Pomocy specyficznej dla kraju/regionu](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Zamówienie odbiorcy z kaucją** — odbiorca tworzy zamówienie odbiorcy w POS. Klient może wpłacić depozyt za zamówienie na podstawie domyślnego procentu depozytu skonfigurowanego na stronie **Zamówienia klientów** w Commerce headquarters (**Parametry handlowe \> Zamówienia klientów**). Commerce przetwarza wpłatę za zamówienie klienta jako transakcję przedpłaty. Podczas księgowania transakcji tworzony jest dziennik płatności i księgowany na stronie **Karta dziennika**. Pole wyboru **Załącznik arkusza przedpłat** na karcie **Płatność** jest automatycznie zaznaczone dla arkusza płatności. Płatność jest rozliczona, a faktura dla odbiorcy jest automatycznie wystawiana w momencie pobrania lub dostarczenia zamówienia.
- **Zamówienie sprzedaży dla centrum obsługi** — Przedstawiciel obsługi klienta tworzy zamówienie sprzedaży w imieniu odbiorcy, a atrybut **przedpłaty** ma wartość **Tak** podczas przechwytywania płatności.

Commerce wykonuje następujące zadania w celu wykonania przedpłaty:

- **Przetwarzaj wpłatę na konto odbiorcy** – Wpłata na konto odbiorcy jest przekazywana do handlu przy użyciu usługi, która synchronizuje dane. Commerce tworzy dla tej płatności transakcję płatności sieci sprzedaży. Podczas zaksięgowania transakcji detalicznej jest księgowany arkusz kasowy lub arkusz płatności odbiorcy. Pole wyboru **Załącznik arkusza przedpłat** na karcie **Płatność** na stronie **Załącznik arkusza** w programie Commerce Headquarters jest automatycznie zaznaczone dla arkusza płatności. Nie można przetworzyć przedpłat, jeśli kwota płatności jest ujemna.
- **Przetwarzaj zamówienie klienta lub zamówienie sprzedaży, które zawiera depozyt** – Klient płaci wymagany depozyt za zamówienie klienta za pomocą Commerce Data Exchange: Usługa w czasie rzeczywistym. Program Commerce tworzy arkusz płatności odbiorcy lub arkusz kasowy, w zależności od metody płatności używanej przez klienta. Pole wyboru **Załącznik arkusza przedpłat** na karcie **Płatność** na stronie **Załącznik arkusza** jest automatycznie zaznaczone dla arkusza w programie Commerce Headquarters. Jeśli klient używa wielu metod płatności do dokonywania płatności częściowych, Commerce przetwarza każdą płatność częściową na podstawie użytej metody płatności.

W przypadku kart kredytowych i portfeli cyfrowych, dla których stosowane są metody płatności kartą kredytową, Commerce wysyła żądanie „przechwycenia” po udanej autoryzacji. (Fundusze są przechwytywane przed zafakturem zamówienia sprzedaży.)

W przypadku anulowania zamówienia odbiorcy kwota przedpłaty zostanie zwrócona, a dla tej kwoty zostanie zaksięgowany arkusz płatności zwrotu. Kwota zwrotu jest obliczana i księgowana na podstawie metody płatności określonej podczas jej zaksięgowania. W programie Commerce można zastosować opłatę za anulowanie w oparciu o wartość procentową ustawioną na stronie **Parametry Commerce** w programie Commerce Headquarters.

W przypadku zwrotu zamówienia odbiorcy zostanie utworzone zamówienie zwrotu i arkusz płatności zwrotów. Podczas zaksięgowania zamówienia zwrotu program Commerce tworzy arkusz płatności odbiorcy lub arkusz kasowy, w zależności od metody płatności użytej przez klienta dla oryginalnej transakcji.
