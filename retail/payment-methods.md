---
title: "Metody płatności"
description: "Każdego typu płatności, który akceptuje detalistą musi być skonfigurowany w handlu detalicznym i handlu w usłudze Microsoft Dynamics 365 dla operacji podczas konfigurowania systemu. W tym artykule opisano typy płatności, które można utworzyć, oraz proces ich konfigurowania."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b887fc5d03ea8982515e92725ce98cc416e56f9e
ms.openlocfilehash: 011beec07bf1ab858892ab1c374f1acf3839e877
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods"></a>Metody płatności

Każdego typu płatności, który akceptuje detalistą musi być skonfigurowany w handlu detalicznym i handlu w usłudze Microsoft Dynamics 365 dla operacji podczas konfigurowania systemu. W tym artykule opisano typy płatności, które można utworzyć, oraz proces ich konfigurowania.

Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają. Jakkolwiek środki pieniężne to najczęściej używana forma płatności, sprzedawcy detaliczni mogą również pobierać płatności w formie czeków, kart, załączników itd. Każdego typu płatności, który akceptuje punkt sprzedaży detalicznej musi być skonfigurowany w usłudze Dynamics 365 dla operacji - Retail podczas konfigurowania systemu. Na poniższej liście opisano każdy typ płatności, który można skonfigurować w usłudze Dynamics 365 dla operacji - detalicznych:

-   **Gotówka** — pieniądze w postaci fizycznej waluty, takie jak banknoty i monety. Ta waluta może być walutą firmy lub walutą lokalną sklepu.
-   **Czek** — dokument zbywalny zlecający płatność określonej kwoty w określonej walucie przez jej pobranie z określonego banku. Czek jest zazwyczaj ważny przez czas nieokreślony lub przez sześć miesięcy od daty wydania, chyba że podano inny okres ważności. Okres ten zależy od banku, który wystawia czek. Istnieją rozmaite typy czeków, np. czeki na zlecenie, czeki kasowe, czeki na okaziciela i czeki na rachunek odbiorcy. Czeki można skonfigurować jako metodę płatności dla każdego sklepu. Czeki zostaną przyjęte w walucie zdefiniowanej na poziomie firmy lub sklepu. Przed rozpoczęciem akceptowania czeku jako płatność w sklepie, należy skonfigurować czeki jako formę płatności.
-   **Waluta** — główna forma płatności inna niż domyślna waluta firmy. Formami waluty są zarówno monety, jak i banknoty. Metoda płatności walutowej uwzględnia wszystkie waluty używane w module Handel detaliczny i inny. Aby można było używać tej metody płatności, należy skonfigurować waluty i określić dla nich informacje o wymianie detalicznej.
-   **Karta** — wszystkie rodzaje kart, które są używane w module Handel detaliczny i inny, takie jak karty debetowe i kredytowe. Warto skonfigurować jeden typ płatności kartą na poziomie organizacji, aby można było akceptować wszystkie rodzaje kart. Następnie na poziomie sklepu można skonfigurować metody płatności dla wszystkich kart lub zestawów kart, które powinny być przetwarzane przy użyciu tych samych ustawień. Aby akceptować płatności kartą w sklepie, należy skonfigurować dostępne na rynku karty producentów, czyli karty debetowe i kredytowe.
-   **Nota kredytowa** — noty wystawione lub realizowane w punkcie sprzedaży. Nota kredytowa może dotyczyć kredytu lub zwrotu i być wystawiona dla zwrotu sprzedaży. W przypadku tylko częściowej realizacji noty kredytowego program wystawia nową notę dla nowego salda. Nowa nota kredytowa ma inny numer. Nota kredytowa może być użyta tylko raz, a system zachowuje zapisy wszystkich numerów, które zostały użyte. Rekord można obejrzeć na stronie **Tabela noty kredytowej**. Odbiorca nie może zrealizować noty kredytowej na kwotę większą niż jej wartość.
-   **Karta upominkowa** — karty upominkowe wystawiane lub realizowane w punkcie sprzedaży. W przypadku kart upominkowych nie są dozwolone nadpłaty.
-   **Konto odbiorcy** — pozwala na obciążenie płatnością konta odbiorcy z poziomu kasy w chwili sprzedaży. Ta metoda płatności służy również do zbierania informacji o sprzedaży lub rabatach właściwych dla odbiorcy, gdy odbiorca dokonuje płatności za pomocą innej metody płatności. W takim przypadku należy skonfigurować informacje właściwe dla odbiorcy.
-   **Punkty lojalnościowe** — punkty, które klienci gromadzą się za pośrednictwem programów lojalnościowych. Jeśli tworzysz programy lojalnościowe, klienci mogą zdobywać punkty i wymienić je na różne sposoby. W niektórych programach lojalnościowych klienci mogą zamieniać punkty na rabaty, lub nawet wykorzystywać je jako formę płatności.

Aby skonfigurować metody płatności w module Handel detaliczny i inny, wykonaj następujące zadania.

1.  Ustaw metod płatności dla organizacji. Utwórz formy płatności akceptowane w całej organizacji.
2.  Tworzenie kart na poziomie organizacji typów i numerów kart. Jeśli są akceptowane karty kredytowe lub debetowe, trzeba utworzyć jedną metodę płatności dla karty, a następnie utwórz kart na poziomie organizacji typów i numerów kart.
3.  Ustawianie metody płatności sklepu. Kojarzenie metod płatności z poszczególnymi sklepami, a następnie wprowadź ustawienia specyficzne dla sklepu, dla każdej metody płatności.
4.  Konfigurowanie karty metod płatności dla sklepów. Dla żadnej metody płatności Karta, akceptowanych przez Magazyn Zakończ konfigurację karty.



