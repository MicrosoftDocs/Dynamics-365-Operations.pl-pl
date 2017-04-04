---
title: Transakcje posiadacza zaliczki
description: "Dowiedz się, jak pracować z transakcje posiadaczy zaliczek w usłudze Microsoft Dynamics 365 dla operacji."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorkerAdvHolderTableListPage_RU
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262554
ms.assetid: 84ff97bb-ae21-4d6d-8160-9325f64134ce
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: c819fbbb4a68dd5b8b192416fedb34827bbf3823
ms.lasthandoff: 03/31/2017


---

# <a name="advance-holder-transactions"></a>Transakcje posiadacza zaliczki

Dowiedz się, jak pracować z transakcje posiadaczy zaliczek w usłudze Microsoft Dynamics 365 dla operacji.

Transakcje dla tych pracowników, którzy są zaliczki, którą posiadacze mogą być księgowane przy użyciu kont posiadacza zaliczki. Identyfikator pracownika, który jest określony dla każdego posiadacza zaliczki może służyć do śledzenia wszystkie transakcje posiadaczy zaliczek. Liczba ta jest interpretowana jako numer konta dla transakcji posiadacza zaliczki w **arkusze finansowe** i **transakcje posiadaczy zaliczek** stron.

## <a name="create-and-post-a-purchase-order-with-advance-holder-details"></a>Tworzenie i Księgowanie zamówienia zakupu z danymi posiadacza zaliczki
Aby uzyskać więcej ogólnych informacji na temat zamówień zakupu, zobacz [Przegląd zamówienia zakupu](/manufacturing/procurement/purchase-order-overview). Jeśli faktura od dostawcy jest tworzony i zaksięgowane z danymi posiadacza zaliczki, salda posiadacza zaliczki zostaną zaksięgowane na koncie Saldo pracownika zamiast konta saldo dostawcy. Aby dodać dane posiadacza zaliczki na zamówienie zakupu, wykonaj następujące czynności:

-   W **warunki płatności** w **ceny i rabatu**, wybierz termin płatności. <!---For more information about **Terms of payment**, see [Define vendor payment terms](http://ax.help.dynamics.com/en/wiki/define-vendor-payment-terms/).-->Wybierz termin płatności, który ma **od posiadacza zaliczki** opcji wybranej na **warunki płatności** strony. Aby uzyskać więcej informacji na temat konfigurowania warunki płatności dla posiadaczy zaliczek, zobacz [posiadacze zaliczek](emea-advance-holders.md).
-   W **posiadacza zaliczki** w **ceny i rabatu** skróconej, wybierz posiadacza zaliczek dla zamówienia zakupu.

Zamówienie zakupu, w procesie księgowania tworzy dwie transakcje dostawcy o przeciwnych kwoty i jednej transakcji posiadacza zaliczki. Bez szczegółów posiadaczy zaliczek jest tworzony tylko jedną transakcja dostawcy.

## <a name="settle-advance-holder-balances-via-a-bank"></a>Zbilansowania sald posiadacza zaliczki za pośrednictwem banku
Po rozliczeniu salda posiadacza zaliczki przez bank, zapisów w arkuszu dla salda posiadacza zaliczki zamknięcia są tworzone w dzienniku głównym. Można skonfigurować kod arkusza i bank w **posiadacze zaliczek** sekcja na **Rozrachunki z dostawcami Parametry** strony. Aby uzyskać więcej informacji, zobacz [posiadacze zaliczek](emea-advance-holders.md). Aby zamknąć Saldo posiadacza zaliczki przez bank, otwórz **rozrachunków z dostawcami**&gt;**posiadacze zaliczek**&gt;**posiadacze zaliczek**. Kliknij **bilans** w okienku akcji, a następnie kliknij pozycję **Zamknij za pośrednictwem banku**. Wprowadź następujące informacje o **Zamknij za pośrednictwem banku** strony.

| Pole                    | opis |
|------------------------------|-------------------|
| **Date of payment**          | Wprowadź datę, która mają być księgowane płatności.|
| **Kwota do przeniesienia** | Wprowadź kwotę salda podczas zamykania. Kwota, która jest wskazana w **kwoty** w **bilans** formularza jest wyświetlany domyślnie. |
| **Automatic**                | Wybierz **automatyczne** pole wyboru, aby utworzyć i zaksięgować dziennik, który jest ustawiony wstępnie na **Rozrachunki z dostawcami Parametry** strony.|

## <a name="settle-advance-holder-balances-via-cash"></a>Zbilansowania sald posiadacza zaliczki za pośrednictwem kasy
Po rozliczeniu salda posiadacza zaliczki za pośrednictwem kasy zapisów w arkuszu dla salda posiadacza zaliczki zamknięcia są tworzone w arkuszu kasowym. Można skonfigurować kod arkusza i środki pieniężne w **posiadacze zaliczek** tab na **Rozrachunki z dostawcami Parametry** strony. Aby uzyskać więcej informacji, zobacz [posiadacze zaliczek](emea-advance-holders.md). Aby zamknąć posiadaczem zaliczki salda za pośrednictwem kasy, otwórz **rozrachunków z dostawcami**&gt;**posiadacze zaliczek**&gt;**posiadacze zaliczek**. Kliknij **bilans** w okienku akcji, a następnie kliknij pozycję **Zamknij za pośrednictwem kasy**. Wprowadź następujące informacje o **Zamknij za pośrednictwem kasy** strony.

| Pole                    | opis
|------------------------------|-----------------|
| **Date of payment**          | Wprowadź datę, która mają być księgowane płatności.|
| **Kwota do przeniesienia** | Wprowadź kwotę salda podczas zamykania. Kwota, która jest wskazana w **kwoty** w **bilans** formularza jest wyświetlany domyślnie. |
| **Automatic**                | Wybierz **automatyczne** pole wyboru, aby utworzyć i automatycznie księgować arkusz który jest ustawiony wstępnie na **Rozrachunki z dostawcami Parametry** strony.     |

Po poślizgu arkusza jest przetwarzany, jeśli kwota w **kwoty podlegającej przekazaniu** pole był ujemny, dokumentu KW jest generowany dla posiadacza zaliczek po zamknięciu sald. Jeśli kwota w **kwoty podlegającej przekazaniu** pole było pozytywne, generowany jest KP.


