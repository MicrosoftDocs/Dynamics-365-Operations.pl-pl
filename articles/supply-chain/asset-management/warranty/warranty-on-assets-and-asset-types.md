---
title: Gwarancje na składniki majątku i typy składników majątku
description: W tym temacie wyjaśniono, jak konfigurować gwarancje składników majątku i typów składników majatku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b13f8aba7e1d2448495f97a4772eb573e08c025
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874608"
---
# <a name="warranty-on-assets-and-asset-types"></a>Gwarancja na składniki majątku i typy składników majątku

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


W tym temacie wyjaśniono, jak konfigurować gwarancje składników majątku i typów składników majatku w module Zarządzanie składnikami majątku.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Konfiguruj gwarancję na typy składników majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Typy składników majątku** \> **Typy składników majątku**.
2. W lewym okienku wybierz typ składnika majątku, do którego ma zostać dołączona umowa gwarancyjna dostawcy, a następnie wybierz opcję **Ustawienia domyślne typu składnika majątku**.
3. Na skróconej karcie **Ogólne** w polu **Gwarancja dostawcy** wybierz umowę.

## <a name="set-up-a-warranty-on-an-asset"></a>Konfiguruj gwarancję na składnik majątku.

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**.
2. Zaznacz składnik i kliknij przycisk **Edytuj**.
3. Na skróconej karcie **Dostawcy** w sekcji **Gwarancja dostawcy** w polu **Gwarancja** wybierz umowę gwarancyjną.
4. W polach **Rozpoczęcie gwarancji** i **Zakończenie gwarancji** wybierz datę początkową i końcową.

    > [!IMPORTANT]
    > Jeśli w polu **Rozpoczęcie gwarancji** zlecenia pracy została wybrana data, gwarancja staje się ważna dla zlecenia dotyczącego tego dnia. Podczas tworzenia zlecenia pracy pole **Rozpoczęcie gwarancji** jest automatycznie ustawiane na datę utworzenia. Można jednak zmienić datę w taki sposób, aby odpowiadała, na przykład, dacie początkowej umowy gwarancyjnej.
    >
    > ![Rysunek 1](media/02-warranty.png)

> [!NOTE]
> W przypadku tworzenia zlecenia pracy dla składnika majątku objętego gwarancją dostawcy, jeśli zlecenie pracy ma oczekiwaną datę rozpoczęcia w okresie gwarancji, zostanie wyświetlone powiadomienie dotyczące umowy gwarancyjnej. W razie konieczności można anulować zlecenie pracy.
