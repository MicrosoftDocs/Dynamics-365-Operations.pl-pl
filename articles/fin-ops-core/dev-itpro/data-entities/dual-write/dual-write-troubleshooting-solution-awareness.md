---
title: Rozwiązywanie problemów związanych ze świadomością rozwiązania
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: aa5ba0cfb127f20012237774fe948c23731eb56f8680d9fa23309e189683dbf3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736357"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Rozwiązywanie problemów związanych ze świadomością rozwiązania

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. A dokładniej, ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="error-on-the-dual-write-page"></a>Błąd na stronie podwójnego zapisu

Na stronie **Podwójny zapis** może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu:

*Jednostka o nazwie „msdyn\_dualwriteentitymap” z namemapping = „Logical” nie została znaleziona w MetadataCache.*

Aby rozwiązać ten problem, upewnij się, że w Dataverse jest zainstalowany podstawowe rozwiązanie podwójnego zapisywania. Podstawowe rozwiązanie dotyczące podwójnego zapisywania jest warunkiem koniecznym do uzyskania świadomości rozwiązania.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]