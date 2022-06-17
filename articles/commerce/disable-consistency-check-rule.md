---
title: Wyłączanie reguł używanych w procesie sprawdzania poprawności transakcji
description: W tym artykule opisano funkcje wyłączania reguł sprawdzania poprawności transakcji wprowadzone w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884884"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Wyłączanie reguł używanych w procesie sprawdzania poprawności transakcji

[!include [banner](../includes/banner.md)]

Sieci handlowe mogą mieć unikatowe dla nich scenariusze i procesy biznesowe. Z tego względu nie wszystkie reguły ujęte w procesie sprawdzania poprawności transakcji handlowych mają zastosowanie do wszystkich sieci handlowych. W celu uwzględnienia różnic rozwiązanie Microsoft Dynamics 365 Commerce oferuje funkcje, których można użyć do wyłączenia reguł, które nie mają zastosowania.

Aby wyświetlić listę reguł dostępnych w procesie sprawdzania poprawności transakcji w danym środowisku oraz stan każdej reguły, należy wybrać kolejno **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce** i wybrać kartę **Weryfikacja transakcji**. Do sprawdzania poprawności transakcji podczas procesu **Sprawdź poprawność transakcji w sklepie** są używane wszystkie włączone reguły — aby transakcje zostały zebrane i zaksięgowane w ramach zestawienia transakcyjnego, dla wszystkich reguł musi zostać uzyskany pomyślny wynik sprawdzania.

Domyślnie stan każdej reguły jest ustawiony na **Włączone**. Z tego względu wszystkie reguły są używane do weryfikacji transakcji, zanim będzie możliwe pobranie ich do zestawień transakcji handlowych. Aby wyłączyć regułę, zmień jej stan na **Wyłączone**. Wyłączone reguły nie są brane pod uwagę, gdy transakcje są weryfikowane w trakcie procesu **Sprawdź poprawność transakcji w sklepie**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
