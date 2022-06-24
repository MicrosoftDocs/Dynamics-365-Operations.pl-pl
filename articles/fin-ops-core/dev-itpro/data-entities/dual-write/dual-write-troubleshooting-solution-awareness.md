---
title: Rozwiązywanie problemów związanych ze świadomością rozwiązania
description: Ten artykuł zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c280eef995664c640e382817dda9d6e1cde154c6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871503"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Rozwiązywanie problemów związanych ze świadomością rozwiązania

[!include [banner](../../includes/banner.md)]





Ten artykuł zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse. A dokładniej, ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.

> [!IMPORTANT]
> Niektóre problemy z tego artykułu mogą wymagać roli administratora systemu lub poświadczeń administratora klienta usługi Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="error-on-the-dual-write-page"></a>Błąd na stronie podwójnego zapisu

Na stronie **Podwójny zapis** może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu:

*Jednostka o nazwie „msdyn\_dualwriteentitymap” z namemapping = „Logical” nie została znaleziona w MetadataCache.*

Aby rozwiązać ten problem, upewnij się, że w Dataverse jest zainstalowany podstawowe rozwiązanie podwójnego zapisywania. Podstawowe rozwiązanie dotyczące podwójnego zapisywania jest warunkiem koniecznym do uzyskania świadomości rozwiązania.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]