---
title: Transakcje posiadacza zaliczki
description: Dowiedz się, jak pracować z transakcjami posiadaczy zaliczek w Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorkerAdvHolderTableListPage_RU
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 262554
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a68c00fc7fc6742da7b2732897fd21e0028f1493
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981877"
---
# <a name="advance-holder-transactions"></a>Transakcje posiadacza zaliczki

[!include [banner](../includes/banner.md)]

Dowiedz się, jak pracować z transakcjami posiadaczy zaliczek.

Transakcje dla pracowników będących posiadaczami zaliczek mogą być księgowane przy użyciu kont posiadaczy zaliczek. Identyfikator pracownika określony dla każdego posiadacza zaliczki może służyć do śledzenia wszystkich transakcji danego posiadacza zaliczki. Ten numer jest pobierany jako numer konta dla transakcji posiadacza zaliczki na stronach **Arkusze finansowe** i **Transakcje posiadacza zaliczki**.

## <a name="create-and-post-a-purchase-order-with-advance-holder-details"></a>Tworzenie i księgowanie zamówienia zakupu z danymi posiadacza zaliczki
Aby uzyskać bardziej ogólne informacje o zamówieniach zakupu, zobacz [Omówienie zamówień zakupu](../../supply-chain/procurement/purchase-order-overview.md). Jeśli faktura od dostawcy zostanie utworzona i zaksięgowana z danymi posiadacza zaliczki, salda posiadacza zaliczki zostaną zaksięgowane na koncie bilansowym pracownika, a nie na koncie bilansowym dostawcy. Aby dodać szczegóły posiadacza zaliczki do zamówienia zakupu, wykonaj następujące czynności:

-   W sekcji **Cena i rabat** w polu **Warunki płatności** wybierz termin płatności. <!---For more information about **Terms of payment**, see [Define vendor payment terms](../accounts-payable/tasks/define-vendor-payment-terms.md).--> Wybierz termin płatności, który ma zaznaczoną opcję **Od posiadacza zaliczki** na stronie **Warunki płatności**. Aby uzyskać więcej informacji na temat konfigurowania warunków płatności dla posiadaczy zaliczek, zobacz [Omówienie posiadaczy zaliczek](emea-advance-holders.md).
-   Na skróconej karcie **Cena i rabat** w polu **Posiadacz zaliczki** wybierz posiadacza zaliczki dla zamówienia zakupu.

Proces księgowania zamówienia zakupu utworzy dwie transakcje z dostawcą o przeciwnych kwotach oraz jedną transakcję posiadacza zaliczki. Bez szczegółów posiadacza zaliczki byłaby tworzona tylko jedna transakcja z dostawcą.

## <a name="settle-advance-holder-balances-via-a-bank"></a>Rozliczanie salda posiadacza zaliczki za pośrednictwem banku
Podczas rozliczania sald posiadaczy zaliczek za pośrednictwem banku zapisy w arkuszu dotyczące zamknięcia tych sald są tworzone w arkuszu finansowym. Można skonfigurować kod dla arkusza i banku w obszarze **Posiadacze zaliczek** na stronie **Parametry modułu rozrachunków z dostawcami**. Aby uzyskać więcej informacji, zobacz [Omówienie posiadaczy zaliczek](emea-advance-holders.md). Aby zamknąć saldo posiadacza zaliczki poprzez bank, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Posiadacze zaliczek** &gt; **Posiadacze zaliczek**. W okienku akcji kliknij przycisk **Saldo**, a następnie kliknij opcję **Zamknij — bank**. Wprowadź poniższe informacje na stronie **Zamknij — bank**:

| Pole                    | opis |
|------------------------------|-------------------|
| **Data płatności**          | Wprowadź dzień, w którym płatność powinna zostać zaksięgowana.|
| **Kwota do przeniesienia** | Wprowadź kwotę salda istniejącą podczas zamknięcia. Domyślnie jest wyświetlana kwota wskazana w polu **Kwota** w formularzu **Saldo**. |
| **Automatycznie**                | Zaznacz pole wyboru **Automatycznie**, aby utworzyć i zaksięgować arkusz wstępnie ustawiony na stronie **Parametry modułu rozrachunków z dostawcami**.|

## <a name="settle-advance-holder-balances-via-cash"></a>Rozliczanie salda posiadacza zaliczki za pośrednictwem kasy
Podczas rozliczenia sald posiadaczy zaliczek za pośrednictwem kasy zapisy w arkuszu dotyczące zamknięcia tych sald są tworzone w arkuszu kasowym. Można skonfigurować kod dla arkusza i kasy na karcie **Posiadacze zaliczek** na stronie **Parametry modułu rozrachunków z dostawcami**. Aby uzyskać więcej informacji, zobacz [Omówienie posiadaczy zaliczek](emea-advance-holders.md). Aby zamknąć saldo posiadacza zaliczki poprzez kasę, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Posiadacze zaliczek** &gt; **Posiadacze zaliczek**. W okienku akcji kliknij przycisk **Saldo**, a następnie kliknij opcję **Zamknij — kasa**. Wprowadź poniższe informacje na stronie **Zamknij — kasa**:

| Pole                    | opis
|------------------------------|-----------------|
| **Data płatności**          | Wprowadź dzień, w którym płatność powinna zostać zaksięgowana.|
| **Kwota do przeniesienia** | Wprowadź kwotę salda istniejącą podczas zamknięcia. Domyślnie jest wyświetlana kwota wskazana w polu **Kwota** w formularzu **Saldo**. |
| **Automatycznie**                | Zaznacz pole wyboru **Automatycznie**, aby automatycznie utworzyć i zaksięgować arkusz wstępnie ustawiony na stronie **Parametry modułu rozrachunków z dostawcami**.     |

Jeśli po przetwarzaniu arkusza kasowego kwota w polu **Kwota do przeniesienia** była ujemna, jest generowany dokument KW dla posiadacza zaliczki po zamknięciu sald. Jeśli kwota w polu **Kwota do przeniesienia** była dodatnia, jest generowany dokument KP.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zaliczki na rzecz pracownika (Europa Wschodnia)](tasks/advance-payment-employee.md)

