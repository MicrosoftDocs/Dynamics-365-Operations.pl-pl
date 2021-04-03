---
title: Dodawanie obliczenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e23d33c6911310cca6aac0df4589e909568a86a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258078"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Dodawanie obliczenia do modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu. Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.


## <a name="add-a-calculation"></a>Dodawanie obliczenia

## <a name="create-calculation-expression"></a>Tworzenie wyrażenia obliczenia
1. Kliknij opcję Edytuj wyrażenie.
2. W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.
3. Kliknij przycisk Sprawdź poprawność.
4. Kliknij przycisk Zamknij.
5. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]