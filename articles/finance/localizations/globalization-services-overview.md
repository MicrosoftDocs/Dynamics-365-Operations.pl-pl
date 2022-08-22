---
title: Usługi globalizacji Dynamics 365
description: Ten artykuł zawiera omówienie usług globalizacji Microsoft Dynamics 365.
author: kfend
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
ms.openlocfilehash: eebf74ab30a544f6561cf5782148d12b58d9c4b7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278241"
---
# <a name="dynamics-365-globalization-services"></a>Usługi globalizacji Dynamics 365

[!include [banner](../includes/banner.md)]

Następujące usługi globalizacji można skonfigurować w celu rozszerzenia możliwości, które istnieją w niektórych usługach online Microsoft Dynamics 365:

- **Usługa Regulatory Configuration Service (RCS)** obsługuje konfigurację różnych typów dokumentów i raportów elektronicznych. RCS zapewnia ulepszoną wersję projektanta raportowania elektronicznego (ER), w którym repozytorium konfiguracji jest samodzielną usługą. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Regulatory Configuration Service](rcs-overview.md).
- **Fakturowanie elektroniczne** łączy konfigurowalne formaty dla przekształceń, podpisów cyfrowych i konfigurowalnych integracji dla łączności z zewnętrznymi usługami sieci web, w tym obsługi certyfikacji i odpowiedzi. Aby uzyskać więcej informacji, zajrzyj do [Faktury elektroniczne](e-invoicing-service-overview.md).
- **Obliczanie podatków** zapewnia większą elastyczność dzięki obsłudze wielu identyfikatorów podatkowych, określaniu kodów podatkowych, projektantowi obliczania podatków i mechanizmowi wykonawczemu, który zapewnia zgodność ze złożonymi przepisami podatkowymi na całym świecie. Aby uzyskać więcej informacji, zobacz [Obliczanie podatku](global-tax-calcuation-service-overview.md).

Te usługi globalizacji zapewniają bezpośrednią integrację z następującymi usługami online Dynamics 365.

| Usługi online | RCS | Fakturowanie elektroniczne | Obliczanie podatku (wersja zapoznawcza) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Tak | Tak | Tak | 
| Dynamics 365 Supply Chain Management | Tak | Tak | Tak | 
| Dynamics 365 Project Operations | Tak | Tak | Nie dotyczy | 
| Dynamics 365 Commerce | Tak | Nie dotyczy | Nie dotyczy | 

> [!NOTE]
> Ze względu na różnice w dostępności lokalizacji geograficznych (geograficznych) platformy Azure dla RCS konfiguracja tej usługi może spowodować przeniesienie danych klientów poza obszar geograficzny wybrany dla odpowiedniej usługi online Dynamics 365. Aby uzyskać więcej informacji, zobacz temat [Dynamics 365 oraz Power Platform: Dostępność, lokalizacja danych, język i lokalizacja](https://aka.ms/rcs/D365Productavailabilityguide).
