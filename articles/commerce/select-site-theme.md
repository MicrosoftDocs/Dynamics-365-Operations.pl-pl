---
title: Wybór motywu witryny
description: W tym temacie opisano sposób ustawiania lub zmieniania motywu witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e3f7f38a0b4b1e0be85d619a1c133d1555706d93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254728"
---
# <a name="select-a-site-theme"></a>Wybór motywu witryny

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób ustawiania lub zmieniania motywu witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Układ i styl witryny (np. czcionki, rozmiary i kolory) są definiowane przez wybrany motyw i mają zastosowanie w odniesieniu do witryny. Motyw jest tworzony i wdrażany przez programistę w firmie użytkownika. Aby zapoznać się z omówieniem motywów, zajrzyj do [Omówienie funkcji motywowania](e-commerce-extensibility/theming.md). Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania motywów, zobacz [Tworzenie nowego motywu](e-commerce-extensibility/create-theme.md).

Domyślnie podczas tworzenia oddziałów jest używany motyw o nazwie **Fabrikam**. Ten motyw domyślny jest dostarczany jako część biblioteki modułu handlu elektronicznego. Po wdrożeniu dodatkowych motywów dla witryny można skonfigurować witrynę tak, aby korzystała z jednego z nich.

## <a name="select-the-site-theme"></a>Wybór motywu witryny

Aby wybrać motyw zastosowany w odniesieniu do witryny, należy wykonać następujące kroki.

1. W środowisku tworzenia witryn przejdź do swojej witryny.
1. Przejdź do **Zarządzanie witryną** \> **Możliwości rozszerzania**.
1. W obszarze **Motyw** wybierz motyw w menu rozwijanym.
1. Aby zastosować wybraną kompozycję do witryny, wybierz opcję **Zapisz i Opublikuj**.

> [!NOTE]
> Wybrany motyw jest publikowany w witrynie po wybraniu opcji **Zapisz i Publikuj** na stronie **Możliwości rozszerzania**. Aby wyświetlić podgląd motywu w witrynie przed zastosowaniem go, można użyć swojego środowiska programistycznego lub piaskownicy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

[Omówienie funkcji motywowania](e-commerce-extensibility/theming.md)

[Tworzenie nowego motywu](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]