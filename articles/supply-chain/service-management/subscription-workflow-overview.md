---
title: Przegląd procesu subskrypcji
description: Ten temat zawiera omówienie przepływu pracy subskrypcji.
author: kamaybac
ms.date: 05/07/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd1484563e9650b9ddae543e3440eec2a3ed075c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983052"
---
# <a name="subscription-workflow-overview"></a>Przegląd procesu subskrypcji 

[!include [banner](../includes/banner.md)]


Pracujesz jako administrator subskrypcji w firmie, która oferuje abonament na konserwację osprzętu oświetleniowego. Klient skontaktował się w sprawie zakupu rocznej subskrypcji.

## <a name="setting-up-subscriptions"></a>Konfigurowanie subskrypcji

Aby skonfigurować subskrypcję, należy najpierw utworzyć grupę subskrypcji dla nowej umowy serwisowej, o ile taka grupa subskrypcji jeszcze nie istnieje. Jeśli grupa już istnieje, to musi zostać tak skonfigurowana, aby klient był rozliczany przez rok i aby przychody z tytułu sprzedaży były naliczane dla każdego miesiąca w roku. Aby uzyskać więcej informacji o ustawianiu subskrypcji, zobacz [Konfigurowanie grup subskrypcji](set-up-subscription-groups.md).

Po utworzeniu grupy subskrypcji można utworzyć subskrypcję. Aby uzyskać więcej informacji na temat tworzenia subskrypcji serwisu, zobacz [Tworzenie subskrypcji serwisu z grupy subskrypcji](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Tworzenie i modyfikowanie transakcji subskrypcji

Po skonfigurowaniu subskrypcji należy utworzyć transakcję opłaty subskrypcyjnej za pierwszy rozliczany okres, czyli za jeden rok. Transakcje są typu **Normalna**. W związku z tym można tworzyć tylko transakcje subskrypcji, których daty początkowa i końcowa odpowiadają okresom utworzonym wcześniej w formularzu **Typy okresu**. Aby uzyskać więcej informacji o transakcjach opłat, zobacz [Tworzenie transakcji opłat subskrypcji](create-subscription-fee-transactions.md).

Po skonfigurowaniu subskrypcji dla klienta przypominasz sobie o wynegocjowanym rabacie o wysokości 10 procent na wszystkie pozycje cennikowe w ofercie. Należy więc obniżyć wysokość już utworzonej opłaty transakcji.

Jeszcze tego samego dnia osoba kontaktowa od klienta dzwoni z informacją, że nadal chcą zawrzeć umowę serwisową na konserwację oświetlenia, ale w ciągu roku jest tam planowana instalacja nowego oświetlenia. W związku z tym konserwacja jest potrzebna tylko na okres do października 2013 roku. Aby zredukować liczbę miesięcy w subskrypcji klienta, trzeba utworzyć nową transakcję opłaty subskrypcji typu **Dni redukcji**. Aby uzyskać więcej informacji o zmniejszaniu liczby dni, zobacz [Zmniejszanie dni na opłaty subskrypcji](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Fakturowanie i naliczanie transakcji subskrypcji

Konfigurowanie subskrypcji zostało zakończone i można rozliczać klienta z tytułu subskrypcji. Aby uzyskać więcej informacji o fakturowaniu subskrypcji, zobacz [Fakturowanie transakcji subskrypcji](invoice-subscription-transactions.md).

Dwa dni później klient zadzwonił z informacją, że subskrypcja powinna być rozliczana w dolarach amerykańskich, a nie w euro. Trzeba więc sporządzić fakturę korygującą oraz utworzyć nową transakcję subskrypcji we właściwej walucie. Aby uzyskać więcej informacji o stosowaniu uznań do transakcji subskrypcji, zobacz [Transakcje subskrypcji kredytu](credit-subscription-transactions.md).

Na koniec każdego miesiąca miesięczne przychody z tytułu subskrypcji od klienta można naliczać na koncie wynikowym i na kontach PWT. Aby uzyskać więcej informacji o naliczaniu przychodów z subskrypcji, zobacz [Naliczanie przychodu z subskrypcji](accrue-subscription-revenue.md).

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]