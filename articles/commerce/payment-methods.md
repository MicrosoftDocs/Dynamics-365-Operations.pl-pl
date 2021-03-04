---
title: Metody płatności
description: Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany na etapie konfiguracji systemu. W tym artykule opisano typy płatności, które można utworzyć, oraz proces ich konfigurowania.
author: rubencdelgado
manager: AnnBe
ms.date: 06/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2b56609de3b2620dcc605c6c6d697cb74c8ed6c1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414952"
---
# <a name="payment-methods"></a>Metody płatności

[!include [banner](includes/banner.md)]

Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany na etapie konfiguracji systemu. W tym artykule opisano typy płatności, które można utworzyć, oraz proces ich konfigurowania.

Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają. Jakkolwiek środki pieniężne to najczęściej używana forma płatności, sprzedawcy detaliczni mogą również pobierać płatności w formie czeków, kart, załączników itd. Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany w Dynamics 365 Commerce na etapie konfiguracji systemu. Poniższa lista zawiera opisuje każdy typ płatności, który można skonfigurować w:

- **Gotówka** — pieniądze w postaci fizycznej waluty, takie jak banknoty i monety. Ta waluta może być walutą firmy lub walutą lokalną sklepu.
- **Czek** — dokument zbywalny zlecający płatność określonej kwoty w określonej walucie przez jej pobranie z określonego banku. Czek jest zazwyczaj ważny przez czas nieokreślony lub przez sześć miesięcy od daty wydania, chyba że podano inny okres ważności. Okres ten zależy od banku, który wystawia czek. Istnieją rozmaite typy czeków, np. czeki na zlecenie, czeki kasowe, czeki na okaziciela i czeki na rachunek odbiorcy. Czeki można skonfigurować jako metodę płatności dla każdego sklepu. Czeki zostaną przyjęte w walucie zdefiniowanej na poziomie firmy lub sklepu. Przed rozpoczęciem akceptowania czeku jako płatność w sklepie, należy skonfigurować czeki jako formę płatności.
- **Waluta** — główna forma płatności inna niż domyślna waluta firmy. Formami waluty są zarówno monety, jak i banknoty. Metoda płatności walutowej uwzględnia wszystkie używane waluty. Aby można było używać tej metody płatności, należy skonfigurować waluty i określić dla nich informacje o wymianie walut.
- **Karta** — wszystkie używane rodzaje kart, takie jak karty debetowe i kredytowe. Warto skonfigurować jeden typ płatności kartą na poziomie organizacji, aby można było akceptować wszystkie rodzaje kart. Następnie na poziomie sklepu można skonfigurować metody płatności dla wszystkich kart lub zestawów kart, które powinny być przetwarzane przy użyciu tych samych ustawień. Aby akceptować płatności kartą w sklepie, należy skonfigurować dostępne na rynku karty producentów, czyli karty debetowe i kredytowe.
- **Nota kredytowa** — noty wystawione lub realizowane w punkcie sprzedaży. Nota kredytowa może dotyczyć kredytu lub zwrotu i być wystawiona dla zwrotu sprzedaży. W przypadku tylko częściowej realizacji noty kredytowego program wystawia nową notę dla nowego salda. Nowa nota kredytowa ma inny numer. Nota kredytowa może być użyta tylko raz, a system zachowuje zapisy wszystkich numerów, które zostały użyte. Rekord można obejrzeć na stronie **Tabela noty kredytowej**. Odbiorca nie może zrealizować noty kredytowej na kwotę większą niż jej wartość.
- **Karta upominkowa** — karty upominkowe wystawiane lub realizowane w punkcie sprzedaży. W przypadku kart upominkowych nie są dozwolone nadpłaty. Wszystkie karty upominkowe powinny mieć mapowania numerów kart. 
- **Konto odbiorcy** — pozwala na obciążenie płatnością konta odbiorcy z poziomu kasy w chwili sprzedaży. Ta metoda płatności służy również do zbierania informacji o sprzedaży lub rabatach właściwych dla odbiorcy, gdy odbiorca dokonuje płatności za pomocą innej metody płatności. W takim przypadku należy skonfigurować informacje właściwe dla odbiorcy.
- **Punkty lojalnościowe** — Liczba punktów gromadzonych przez klientów w trakcie programów lojalnościowych. Jeśli utworzysz programy lojalnościowe, klienci będą mogli zdobywać punkty i wykorzystywać je na różne sposoby. W niektórych programach lojalnościowych klienci mogą zamieniać punkty na rabaty, lub nawet wykorzystywać je jako formę płatności.

Aby skonfigurować metody płatności , należy wykonać następujące zadania:

1. Ustaw metod płatności dla organizacji. Utwórz formy płatności akceptowane w całej organizacji.
2. Utwórz typy i numery kart na poziomie organizacji. Jeśli będą przyjmowane karty kredytowe lub debetowe, trzeba utworzyć jeden typ metody płatności kartami, a następnie utworzyć typy i numery kart na poziomie organizacji.
3. Ustaw formę płatności w sklepie. Skojarz typy metod płatności z poszczególnymi sklepami, a następnie wprowadź dla każdego typu metody płatności ustawienia właściwe dla sklepu.
4. Skonfiguruj metody płatności kartą dla sklepów. Skonfiguruj karty dla każdej formy płatności akceptowanej w sklepie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]