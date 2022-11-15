---
title: Znane problemy ze scalaniem infrastruktury Dynamics 365 Human Resources
description: W tym artykule wymieniono problemy, które mogą wystąpić podczas scalania infrastruktury Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5f5981801317ad9647f57a0f68f9b67b592256ab
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752698"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Znane problemy ze scalaniem infrastruktury Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Udostępnione środowiska Dataverse

Środowisko podwójnego zapisu nie obsługuje łączenia dwóch środowisk aplikacji finansowych i operacyjnych z tym samym środowiskiem Dataverse. Jeśli istnieje środowisko Dataverse, które jest współdzielone z następującymi elementami, należy zduplikować środowisko Dataverse lub je podzielić:

- Aplikacja finansowa i operacyjna
- Bieżące środowisko Human Resources

## <a name="environment-type-requirements"></a>Wymagania dotyczące typu środowiska

Przed migracją są wymagane następujące typy środowiska:

- Jeśli nie masz autonomicznych środowisk piaskownicy, musisz je utworzyć, aby zweryfikować migrację.
- Jeśli istnieje wiele środowisk autonomicznych produkcji, jedno z nich można migrować. Skontaktuj się z pomocą techniczną firmy Microsoft, aby oznaczyć inne środowiska jako piaskownice.

## <a name="teams-integration"></a>Integracja programu Teams

Istniejąca aplikacja Human Resources w aplikacji Teams jest obecnie przenoszona do rozwiązania Microsoft Power Platform. Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](hr-admin-teams-leave-app.md).

