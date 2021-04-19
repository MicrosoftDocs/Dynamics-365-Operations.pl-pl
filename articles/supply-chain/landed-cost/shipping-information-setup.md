---
title: Konfiguracja informacji o wysyłce
description: W tym temacie opisano, jak skonfigurować informacje o wysyłce dla modułu Koszt z wyładunkiem.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 74ac7e0eac545369eef1a48f0085c820a4728e75
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833696"
---
# <a name="shipping-information-setup"></a>Konfiguracja informacji o wysyłce

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak skonfigurować informacje o wysyłce dla modułu **Koszt z wyładunkiem**.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Opis towarów

Opisy towarów ułatwiają identyfikację podróży, kontenera wysyłkowego lub folio towarów i towarów w nich zawarte. Możesz wybrać opis towarów w nagłówku kontenera wysyłkowego lub nagłówku folio.

Aby pracować z opisami towarów, przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o wysyłce \> Opis towaru**. Można tam wyświetlać, otwierać, tworzyć i usuwać rekordy opisów towarów. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Opis towarów | Wprowadź unikalną nazwę / numer identyfikacyjny dla rodzaju towarów, które będą używać tego opisu. |
| opis | Umożliwia wprowadzenie opisu typu towarów w tej kategorii. |

## <a name="vessels"></a><a name="vessels"></a>Statki

Środek transportu to niepowtarzalna nazwa statku lub środka transportu, z którego korzysta przedsiębiorstwo żeglugowe lub agencja. W przypadku tworzenia podróży należy zawsze wybrać lub wprowadzić środek transportu dla niego. Jeśli często używasz tych samych statków, możesz przyspieszyć i ułatwić tworzenie nowej podróży, tworząc rekord statku dla każdego z nich, umożliwiając użytkownikom wybór statku z listy zamiast ręcznego wprowadzania nazwy lub numeru każdego z nich. czas.

Aby pracować ze statkami, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Środki transportu**. Można tam wyświetlać, otwierać, tworzyć i usuwać środków transportu. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Statek | Wprowadź unikatową nazwę/numer identyfikacyjny wysyłki, która będzie używana do transportu towarów w podróży. |
| opis | Wprowadź opis środka transportu. Zwykle ten opis określa nazwę firmy przewozowej i firmy przewozowej/agenta. |
| Metoda dostawy | Umożliwia wybranie trybu dostawy używanego przez środek transportu (np. _Samolot_, _Ocean_ lub _Pociąg_). |

## <a name="exporters"></a>Eksporterzy

Każdy rekord eksportera identyfikuje dostawcę lub eksportera, który można zdefiniować jako dostawcę dla podróży. Eksporter może być skojarzony z podróżą i używany do raportowania.

Aby pracować ze eksporterami, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Eksporterzy**. Można tam wyświetlać, otwierać, tworzyć i usuwać eksporterów. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Eksporter | Wprowadź niepowtarzalną nazwę / numer identyfikacyjny eksportera towarów przewożonych w podróży. |
| opis | Wprowadź opis eksportera. Zwykle ten opis określa pełną nazwę firmy przewozowej i firmy przewozowej/agenta. |

## <a name="commodity-codes"></a>Kody asortymentu

Używasz kodów towarów, aby pomóc w identyfikacji celnej i obliczaniu stawek celnych dla towarów podczas podróży. Kody asortymentu można wybierać na stronie **Zwolnione produkty**.

Aby pracować z kodami asortymentu, przejdź do **Koszty dostawy \> Konfiguracja informacji o wysyłce \> Kody asortymentu**. Można tam wyświetlać, otwierać, tworzyć i usuwać kody asortymentu. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Kod asortymentu | Umożliwia wprowadzenie unikatowego kodu asortymentu tego typu. |
| opis | Umożliwia wprowadzenie opisu typu asortymentu. |

## <a name="customs-description"></a>Opis płatności celnych

Opisy celne ułatwiają identyfikowanie towarów na potrzeby celne. Możesz wybrać opis cła na stronie **Zwolnione produkty** lub w wierszach zamówienia zakupu.

Aby pracować z opisami cła, przejdź do **Koszt z wyładunkiem \> Konfiguracja informacji o wysyłce \> Opis cła**. Można tam wyświetlać, otwierać, tworzyć i usuwać rekordy opisów cła. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Opis płatności celnych | Wprowadź unikalny kod dla tego typu klasyfikacji celnej. Często kod ten będzie oficjalnym opisem dostarczonym przez organ celny w celu opisu i jakościowej wartości towarów. |
| opis | Wprowadź opis klasyfikacji celnej. |
