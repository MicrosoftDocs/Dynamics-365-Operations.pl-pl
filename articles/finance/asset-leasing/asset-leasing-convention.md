---
title: Konwencje wynajmu składnika majątku
description: Ten temat opisuje konwencje wynajmowanych składników majątku.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 67c4d2b7162cf6bda2eedfecef43ff0b216e6e6c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881815"
---
# <a name="asset-leasing-conventions"></a>Konwencje wynajmu składnika majątku

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ten temat opisuje konwencje wynajmowanych składników majątku. Konwencje wynajmu są używane do określania daty rozpoczęcia księgi wynajmu. Jeśli konwencja wynajmu ma wartość **Brak**, data rozpoczęcia jest taka sama jak data rozpoczęcia wynajmu (to jest wartość pola **Data rozpoczęcia wynajmu**). Jeśli umowa leasingu jest ustawiona na **Pełny miesiąc**, datą rozpoczęcia jest pierwszy dzień miesiąca, w którym przypada data rozpoczęcia leasingu.

Data rozpoczęcia określa datę rozpoczęcia okresu umorzenia zobowiązań i harmonogramów amortyzacji środków trwałych. Wydatki na odsetki i wydatki amortyzacyjne są księgowane w dniu zakończenia okresu odpowiednich harmonogramów. Początkowy wpis arkusza rozpoznawania i korekty jest księgowany w dniu rozpoczęcia.

> [!NOTE]
> Funkcję konwencji wynajmu należy włączyć za pomocą funkcji Zarządzanie funkcjami. W obszarze roboczym **Zarządzanie funkcjami** znajdź i wybierz funkcję o nazwie **Konwencja dzierżawy dla funkcji wynajmu środków trwałych**, a następnie wybierz opcję **Włącz teraz**.

Konfiguracje księgi środków trwałych są przypisywane do konwencji wynajmu.

Aby wyświetlić lub przypisać konwencję wynajmu, należy wykonać następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Księgi wynajmu**.
2. W polu **Konwencja wynajmu** wybierz jedną z następujących wartości.

    | Konwencja wynajmu | opis |
    |--------------------|-------------|
    | None               | Harmonogramy umorzenia zobowiązań i amortyzacji środków trwałych rozpoczynają się od daty rozpoczęcia wynajmu, ponieważ data rozpoczęcia jest równa dacie rozpoczęcia wynajmu. Data zakończenia jest o miesiąc późniejsza. Ta konwencja wynajmu nie gwarantuje, że odsetki będą księgowane ostatniego dnia każdego miesiąca. |
    | Pełny miesiąc         | W przypadku dzierżaw o dacie rozpoczęcia, która ma miejsce o dowolnej godzinie w miesiącu, amortyzacja zobowiązań i plany amortyzacji środków trwałych zaczynają się do naliczania wydatków w pierwszym dniu tego miesiąca. Ta konwencja wynajmu gwarantuje naliczanie odsetek w ostatnim dniu każdego miesiąca. |

3. Wybierz opcję **Zapisz**.

Po utworzeniu wynajmu data rozpoczęcia każdej książki jest automatycznie wprowadzana na podstawie wprowadzonej daty rozpoczęcia leasingu i konwencji wynajmu określonej dla książki.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
