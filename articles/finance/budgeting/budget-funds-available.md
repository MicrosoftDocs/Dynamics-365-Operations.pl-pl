---
title: Dostępne środki budżetowe
description: W tym artykule przedstawiono funkcję dostępnych środków budżetów i przedstawiono informacje ułatwiające konfigurowanie kontroli budżetu w celu optymalizacji zarządzania zasobami finansowymi organizacji.
author: RyanCCarlson2
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b6f94931ba3514c1c66d80b64846d882861d555c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898248"
---
# <a name="budget-funds-available"></a>Dostępne środki budżetowe

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule przedstawiono funkcję dostępnych środków budżetów i przedstawiono informacje ułatwiające konfigurowanie kontroli budżetu w celu optymalizacji zarządzania zasobami finansowymi organizacji.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Rozszerzona funkcja obliczania dostępnych środków budżetowych

Funkcja **Śledź tylko kwoty w obliczeniach dostępnych środków budżetowych** umożliwia śledzenie podstawowych tabel kontroli budżetu dla typów i stanów dokumentów, na podstawie ustawień na stronie **Definiowanie parametrów kontroli budżetu**.

Niektóre opcje konfiguracji kontroli budżetu muszą mieć określone ustawienia, aby funkcja działała poprawnie. Te opcje są zaznaczone lub wyczyszczone na karcie **Dostępne środki budżetowe** na stronie **Definiowanie parametrów kontroli budżetu**. W poniższej tabeli przedstawiono ustawienia wymagane dla funkcji dostępnych funduszy budżetowych.

| W przypadku zaznaczenia pola tej opcji | Należy również wybrać tę opcję |
| ------------------------- | -------------------------------- |
| Rezerwy w budżecie na przyszłe zobowiązania niewiążące | Rezerwy w budżecie dla przyszłych zobowiązań wiążących *i* Wydatki rzeczywiste |
| Rezerwy w budżecie dla przyszłych zobowiązań wiążących | Wydatki zaksięgowane |
| Rezerwy w budżecie dla przyszłych zobowiązań wiążących z dokumentami typu Zapotrzebowania na zakup | Rezerwy w budżecie na przyszłe zobowiązania niewiążące |

Ta funkcja wpływa tylko na nowe dokumenty. Kwoty istniejących dokumentów będą nadal śledzone i pokazywane w statystyce kontroli budżetu do czasu zmiany ustawienia dostępnych funduszy budżetowych i aktywowania nowej konfiguracji kontroli budżetu. Na tym etapie dane śledzenia budżetu zostaną usunięte z dokumentów, które zostały usunięte z obliczeń dostępnych funduszy budżetowych.

Zaleca się pozostawienie pustego pola opcji **Niezaksięgowane wydatki rzeczywiste**. Jeśli ta opcja jest zaznaczona, czasochłonne obliczanie kontroli budżetu będzie wykonywane na niezaksięgowanych dokumentach, takich jak oczekujące faktury od dostawcy.
