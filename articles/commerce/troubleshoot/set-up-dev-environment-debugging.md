---
title: Skonfiguruj środowisko programowe dla usług e-commerce do debugowania względem maszyny wirtualnej warstwy 1 Retail Server
description: W tym temacie wyjaśniono, jak skonfigurować środowisko programistyczne handlu elektronicznego w celu debugowania na maszynie wirtualnej (VM) serwera Tier 1 Retail Server.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0f5586112d168f8fa84f97d110403b0bec82e5cca4e963a92f1c283a17c972ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715315"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Skonfiguruj środowisko programowe dla usług e-commerce do debugowania względem maszyny wirtualnej warstwy 1 Retail Server

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować środowisko programistyczne handlu elektronicznego w celu debugowania na maszynie wirtualnej (VM) serwera Tier 1 Retail Server.

## <a name="description"></a>opis

Microsoft Dynamics 365 Commerce Środowiska warstwy 1 są zwykle wdrażane w środowiskach uruchomieniowych Commerce Runtime (CRT) i w punkcie sprzedaży (POS). Są to środowiska autonomiczne. Ze względu na charakter oprogramowania jako usługi (Rodzaju usług) architektura nie obejmuje składników systemu e-commerce.

W niektórych scenariuszach można przetestować wywołania rozszerzeń w środowisku warstwy 1, aby było możliwe debugowanie rozszerzeń z składników usługi e-commerce. Aby przeczytać ogólne instrukcje, zobacz [Debugowanie względem środowiska projektowego Commerce w warstwie 1 Commerce](../e-commerce-extensibility/debug-tier-1.md).

Podczas debugowania względem środowiska warstwy 1, ponieważ witryna wywołuje teraz inny serwer detaliczny, wywołania między serwerami mogą powodować różne błędy związane z zasadami zabezpieczeń zawartości.

Na poniższej ilustracji pokazano przykład błędu, który może wystąpić, gdy wariant został wybrany na stronie szczegółów produktu.

![Błąd podczas wyboru wariantu na stronie szczegółów produktu.](media/unhandled-rejection-error.jpg)

Na poniższej ilustracji pokazano przykład podobnego błędu w narzędziach debugera przeglądarki (F12 Developer Tools). W komunikacie o błędzie wymieniono naruszenie dyrektywy zasad zabezpieczeń zawartości.

![Błąd narzędzi debugera.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Rozwiązanie

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Wyłączanie zasad zabezpieczeń zawartości dla witryny w Konstruktorze witryn portalu Commerce

1. Wybierz witrynę, nad która pracujesz.
1. Wybierz **Ustawienia**, a następnie wybierz **Rozszerzenia**.
1. Na karcie **Zasady zabezpieczeń** zawartość wybierz pozycję **Wyłącz zasady zabezpieczeń zawartości**.
1. Wybierz **Zapisz i opublikuj**.

> [!NOTE]
> Rejestracja b2C (Business-to-consumer) nie działa w lokalnym środowisku programisty. Można jednak w razie potrzeby użyć funkcji realizacji transakcji gościa lub utworzyć model strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Rozpoczynanie wdrażania rozszerzania handlu elektronicznego](../e-commerce-extensibility/sdk-getting-started.md)

[Zarządzanie zasadami zabezpieczeń zawartości w witrynie handlu elektronicznego](../manage-csp.md)
