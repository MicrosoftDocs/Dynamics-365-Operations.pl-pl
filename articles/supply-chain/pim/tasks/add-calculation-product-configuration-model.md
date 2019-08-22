---
title: Dodawanie obliczenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39450b5aef2fb7b57492a52011f4b0db9dc8ff2e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845054"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Dodawanie obliczenia do modelu konfiguracji produktu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu. Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.


## <a name="add-a-calculation"></a>Dodawanie obliczenia

## <a name="create-calculation-expression"></a>Tworzenie wyrażenia obliczenia
1. Kliknij opcję Edytuj wyrażenie.
2. W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.
3. Kliknij przycisk Sprawdź poprawność.
4. Kliknij przycisk Zamknij.
5. Kliknij przycisk OK.

