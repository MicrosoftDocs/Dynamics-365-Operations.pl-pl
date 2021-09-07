---
title: Rozwiązywanie problemów związanych ze świadomością rozwiązania
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b53e07f69992a567d5b300ae1f2b24b74541d176
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416359"
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