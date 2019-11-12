---
title: Wyłącz reguły w sprawdzaniu spójności transakcji sprzedaży detalicznej
description: W tym temacie opisano funkcje wyłączania reguł sprawdzania spójności transakcji sprzedaży detalicznej wprowadzone w rozwiązaniu Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586304"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Wyłącz reguły w sprawdzaniu spójności transakcji sprzedaży detalicznej 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Sieci handlowe mogą mieć unikatowe dla nich scenariusze i procesy biznesowe. Z tego względu nie wszystkie domyślnie zainstalowane w sprawdzaniu spójności transakcji sprzedaży detalicznej reguły są dostępne dla wszystkich sieci handlowych. W celu uwzględnienia różnic rozwiązanie Microsoft Dynamics 365 Retail oferuje funkcje, których można użyć do wyłączenia nie mających zastosowania reguł.

Aby wyświetlić listę reguł dostępnych w sprawdzaniu spójności transakcji sprzedaży detalicznej w swoim środowisku i zobaczyć stan każdej reguły, przejdź do **Handel detaliczny \> Ustawienia centrali \> Parametry \> Parametry sieci sprzedaży** i wybierz kartę **Weryfikacja transakcji**.

Domyślnie stan każdej reguły jest ustawiony na **Włączone**. Z tego względu wszystkie reguły są używane do weryfikacji transakcji sprzedaży detalicznej przed pobraniem ich do zestawień. Aby wyłączyć regułę, zmień jej stan na **Wyłączone**. Wyłączone reguły nie są brane pod uwagę, gdy transakcje sprzedaży detalicznej są weryfikowane w trakcie procesu obliczania zestawień.

Aby pominąć cały proces weryfikacji bez względu na włączone reguły, przejdź do **Handel detaliczny \> Ustawienia centrali \> Parametry \> Parametry sieci sprzedaży**, a następnie w karcie **Weryfikacja transakcji** ustaw opcję **Wyłącz sprawdzanie spójności transakcji sieci sprzedaży** na wartość **Tak**. Po ustawieniu tej opcji na **Nie** nie można ponownie ustawić jej na **Tak** w interfejsie użytkownika.
