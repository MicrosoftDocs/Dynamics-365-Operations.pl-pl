---
title: Konfigurowanie samoobsługi pracownika etatowego
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e0c59eb8db5a97405e87922cc65f3eb74bee48e
ms.sourcegitcommit: b101c21f972fdad2667431f712222e040cd69d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2021
ms.locfileid: "7898447"
---
# <a name="configure-employee-self-service"></a>Konfigurowanie samoobsługi pracownika etatowego

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W aplikacji Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze **Samoobsługa pracownika etatowego**. Kafelki planów świadczeń kierują użytkowników do planów świadczeń, do których są uprawnieni..

## <a name="set-up-a-benefit-plans-tile"></a>Konfigurowanie kafelka planów świadczeń

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.

2. Kliknij kartę **Ustawienia kafelka planów świadczeń**, a następnie wybierz opcję **Nowy**.

3. Określ wartości dla następujących pól.

   | Pole | Opis |
   | --- | --- |
   | **Kod typu planu** | Typ planu wyświetlany, gdy ten kafelek jest wybrany w obszarze **Samoobsługa świadczeń**. |
   | **Identyfikator kafelka** | Unikatowy identyfikator dla kafelka. |
   | **Tekst etykiety kafelka** | Tekst, który będzie wyświetlany dla kafelka w obszarze **Samoobsługa świadczeń**. |
   | **opis** | Opis kafelka. |
   | **Obraz tła kafelka** | Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie). |
   | **Śledź otwartą rejestrację** | Wybierz tę opcję, aby śledzić postęp otwartej rejestracji dla tego typu planu. Mogą być na przykład tworzone plany, gdzie **Typ planu = Inny**. Te plany mogą być planami opcjonalnymi, dla których nie chcesz śledzić postępu rejestracji. Jeśli nie wybierzesz tego typu planu, ten typ planu będzie ignorowany podczas śledzenia postępu rejestracji lub zakończenia rejestracji na karcie **Otwarta rejestracja**. To ustawienie dotyczy typu planu wybranego dla wszystkich okresów i firm. |

4. Wybierz opcję **Zapisz**.

## <a name="set-up-a-flex-credit-plan-tile"></a>Konfigurowanie kafelka planu kredytu elastycznego

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.

2. Kliknij kartę **Ustawienia kafelka planu kredytu elastycznego**, a następnie wybierz opcję **Nowy**.

3. Określ wartości dla następujących pól.

   | Pole | Opis |
   | --- | --- |
   | **Identyfikator kredytu świadczenia** | Plany elastycznych programów kredytowych, które będą wyświetlane, gdy ten kafelek jest wybrany w obszarze **Samoobsługa świadczeń**. |
   | **Identyfikator kafelka** | Unikatowy identyfikator dla kafelka. |
   | **Tekst etykiety kafelka** | Tekst, który będzie wyświetlany dla kafelka w obszarze **Samoobsługa świadczeń**. |
   | **opis** | Opis kafelka. |
   | **Obraz tła kafelka** | Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie). |
   | **Śledź otwartą rejestrację** | Wybierz tę opcję, aby śledzić postęp otwartej rejestracji dla tego typu planu. Mogą być na przykład tworzone plany, gdzie **Typ planu = Inny**. Te plany mogą być planami opcjonalnymi, dla których nie chcesz śledzić postępu rejestracji. Jeśli nie wybierzesz tego typu planu, ten typ planu będzie ignorowany podczas śledzenia postępu rejestracji lub zakończenia rejestracji na karcie **Otwarta rejestracja**. To ustawienie dotyczy typu planu wybranego dla wszystkich okresów i firm. |

4. Wybierz opcję **Zapisz**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
