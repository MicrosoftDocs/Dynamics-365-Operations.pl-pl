---
title: Automatyczne tworzenie zleceń serwisowych
description: Zlecenia serwisowe można generować na podstawie umowy serwisowej w trakcie okresu ważności umowy serwisowej.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 53369ef2b7ff93ae4f0523accbc31cc88575a383
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010679"
---
# <a name="automatically-create-service-orders"></a>Automatyczne tworzenie zleceń serwisowych 

[!include [banner](../includes/banner.md)]


Zlecenia serwisowe można generować na podstawie umowy serwisowej w trakcie okresu ważności umowy serwisowej.

Wszystkie zlecenia serwisowe generowane na podstawie umowy serwisowej są dołączone do tej umowy serwisowej.

Zlecenia serwisowe są generowane automatycznie na podstawie następujących ustawień:

  - Interwału umowy serwisowej skonfigurowanego w wierszach tej umowy. Interwał umowy serwisowej określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej. Aby uzyskać więcej informacji, zobacz [Interwały serwisu](service-intervals.md).

  - Okresu serwisu zdefiniowanego w polach **Od dnia** i **Do dnia** w formularzu **Utwórz zlecenia serwisowe**. Aby uzyskać więcej informacji, zobacz [Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md).

  - Opcji **Łączenie zleceń serwisowych** w nagłówku umowy serwisowej. Ta opcja określa, czy wiersze zlecenia serwisowego wygenerowane na podstawie umowy serwisowej mają łączyć zlecenia serwisowe według kryterium pracownika, zadania serwisowego, przedmiotu serwisu lub umowy serwisowej. Aby uzyskać więcej informacji, zobacz [Łączenie zleceń serwisowych](combine-service-orders.md).

  - Opcji **Okno czasu** w wierszu umowy serwisowej. Okno czasowe określa, jak daleko wiersz zlecenia serwisowego może być przesunięty względem jego obliczonej daty. Aby uzyskać więcej informacji, zobacz [Okna czasu](time-windows.md).


> [!NOTE]
> <P>Jeśli dzień określony dla zlecenia serwisowego nie jest otwarty w kalendarzu wybranym w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG>, pojawi się komunikat informujący o konflikcie kalendarza. Można bez obaw zignorować ten komunikat. Zlecenie serwisowe zostanie utworzone, nawet mimo że dzień jest zamknięty w kalendarzu.</P>

## <a name="example-1"></a>Przykład 1

Umowa serwisowa obowiązuje od 1 stycznia 2012 r. do 31 grudnia 2012 r. Jeśli okres serwisu określony w formularzu **Utwórz zlecenia serwisowe** sięga od 1 listopada 2012 r. do 1 lutego 2013 r., zlecenia serwisowe będą tworzone od 1 listopada 2012 r. do 31 grudnia 2012 r.

## <a name="example-2"></a>Przykład 2

Umowa serwisowa obowiązuje od 1 stycznia 2012 r. do 31 grudnia 2012 r. Do umowy serwisowej są dołączone dwa wiersze umowy serwisowej. Pierwszy wiersz umowy serwisowej ma datę rozpoczęcia 2 stycznia 2012 r., a datę zakończenia 1 marca 2012 r. Drugi wiersz umowy serwisowej ma datę rozpoczęcia 1 kwietnia 2012 r., a datę zakończenia 31 grudnia 2012 r. W formularzu **Utwórz zlecenia serwisowe** określasz okres sięgając od 1 października 2012 r. do 31 grudnia 2012 r. W efekcie zlecenia serwisowe będą generowane tylko dla drugiego wiersza umowy serwisowej, ponieważ daty początkowa i końcowa pierwszego wiersza umowy przypadają przed zdefiniowanym okresem zlecenia serwisowego.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]