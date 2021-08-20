---
title: Gwarancje na składniki majątku i typy składników majątku
description: W tym temacie wyjaśniono, jak konfigurować gwarancje składników majątku i typów składników majatku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bcfbd56f5fa1491f13ea65c5fb3d70659c3b945276813d7c1c922c849bf8e3a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751177"
---
# <a name="warranties-on-assets-and-asset-types"></a>Gwarancje na składniki majątku i typy składników majątku

[!include [banner](../../includes/banner.md)]

 


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
    > ![Strona Zlecenie pracy.](media/02-warranty.png)

> [!NOTE]
> W przypadku tworzenia zlecenia pracy dla składnika majątku objętego gwarancją dostawcy, jeśli zlecenie pracy ma oczekiwaną datę rozpoczęcia w okresie gwarancji, zostanie wyświetlone powiadomienie dotyczące umowy gwarancyjnej. W razie konieczności można anulować zlecenie pracy.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]