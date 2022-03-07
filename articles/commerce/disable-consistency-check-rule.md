---
title: Wyłączanie reguł używanych w procesie sprawdzania poprawności transakcji
description: W tym temacie opisano funkcje wyłączania reguł sprawdzania poprawności transakcji wprowadzone w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 12/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: cdaea51b4c84e6a62f0eb9412315ae77b4c11503
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919534"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Wyłączanie reguł używanych w procesie sprawdzania poprawności transakcji

[!include [banner](../includes/banner.md)]

Sieci handlowe mogą mieć unikatowe dla nich scenariusze i procesy biznesowe. Z tego względu nie wszystkie reguły ujęte w procesie sprawdzania poprawności transakcji handlowych mają zastosowanie do wszystkich sieci handlowych. W celu uwzględnienia różnic rozwiązanie Microsoft Dynamics 365 Commerce oferuje funkcje, których można użyć do wyłączenia reguł, które nie mają zastosowania.

Aby wyświetlić listę reguł dostępnych w procesie sprawdzania poprawności transakcji w danym środowisku oraz stan każdej reguły, należy wybrać kolejno **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce** i wybrać kartę **Weryfikacja transakcji**. Do sprawdzania poprawności transakcji podczas procesu **Sprawdź poprawność transakcji w sklepie** są używane wszystkie włączone reguły — aby transakcje zostały zebrane i zaksięgowane w ramach zestawienia transakcyjnego, dla wszystkich reguł musi zostać uzyskany pomyślny wynik sprawdzania.

Domyślnie stan każdej reguły jest ustawiony na **Włączone**. Z tego względu wszystkie reguły są używane do weryfikacji transakcji, zanim będzie możliwe pobranie ich do zestawień transakcji handlowych. Aby wyłączyć regułę, zmień jej stan na **Wyłączone**. Wyłączone reguły nie są brane pod uwagę, gdy transakcje są weryfikowane w trakcie procesu **Sprawdź poprawność transakcji w sklepie**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
