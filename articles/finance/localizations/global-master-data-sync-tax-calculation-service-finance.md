---
title: Synchronizuj ustawienia podatku z usługi obliczania podatku z usługą Dynamics 365 Finance
description: W tym artykule wyjaśniono, jak synchronizować dane główne ustawień podatków z usługi obliczania podatku z Microsoft Dynamics 365 Finance.
author: wangchen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegration, TaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b017a19834998e1c493b0a38c1b50accd8c7e630
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853165"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Synchronizuj ustawienia podatku z usługi obliczania podatku z usługą Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak synchronizować dane główne ustawień podatków z usługi obliczania podatku z Microsoft Dynamics 365 Finance.

Po wykonaniu wymaganych czynności konfiguracyjnych w [Rozpocznij z obliczaniem podatków](global-get-started-with-tax-calculation-service.md) następujące dane konfiguracji podatków są automatycznie synchronizowane z usługi obliczania podatków do Finansów.

## <a name="sales-tax-code"></a>Kod podatku

| Usługa obliczania podatku           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Kod podatku                          | Kod podatku                      |
| Opis                       | Nazwa                                |
| Dane wejściowe użytkownika                        | Okres rozliczeniowy                   |
| Dane wejściowe użytkownika                        | Grupa księgowania                |
| Dane wejściowe użytkownika                        | Waluta podatku                  |
| Skonfigurowano ujemną stawkę podatku | Zezwalaj na ujemny procent podatku |

## <a name="tax-value"></a>Wartość podatku

| Usługa obliczania podatku | Finance                   |
| ----------------------- | ------------------------- |
| Początkowa data transakcji   | Data rozpoczęcia                 |
| Końcowa data transakcji     | Data zakończenia                   |
| Minimalna kwota          | Dolny limit             |
| Liczba maksymalna          | Maksymalny limit             |
| Stawka podatku                | Wartość                     |
| Stawka nie podlegającej odliczeniu     | Procent nie podlegający odliczeniu |

## <a name="tax-limits"></a>Limity podatkowe

| Usługa obliczania podatku | Finance           |
| ----------------------- | ----------------- |
| Początkowa data transakcji   | Data rozpoczęcia         |
| Końcowa data transakcji     | Data zakończenia           |
| Minimalna kwota podatku      | Minimalny podatek |
| Maksymalna kwota podatku      | Maksymalny podatek |

## <a name="sales-tax-group"></a>Grupa podatków

| Usługa obliczania podatku                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Grupa podatków                                       | Grupa podatków                            |
| Kody podatków w tej grupie podatków                  | Kody podatków w ramach tej grupy podatków |
| Kod podatku jest oznaczony jako **Zwolnienie**         | Zwolnienie                                     |
| Kod podatku jest oznaczony jako **Zwolnienie**         | Kod zwolnienia                                |
| Oznacz kod podatku jako **Jest opłata zwrotna** | Obciążenie odwrotne                             |
| Kod podatku jest oznaczony jako **Jest opodatkowane**        | Podatek nienaliczony                                    |

## <a name="item-sales-tax-group"></a>Grupa podatków dla pozycji

| Usługa obliczania podatku             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Grupa podatków dla pozycji                      | Grupa podatków dla pozycji                            |
| Kody podatkowe w ramach tej grupy podatkowej pozycji | Kody podatku w ramach tej grupy podatku towaru |

Po zakończeniu synchronizacji kontynuuj utrzymanie pozostałych parametrów w finansach na potrzeby księgowania i raportowania.

> [!NOTE]
> Synchronizacja ustawień podatku z finansów do usługi obliczania podatku nie jest obsługiwana. W przypadku istniejącego środowiska finansowego najpierw utwórz konfigurację podatku w usłudze obliczania podatku. Następnie zsynchronizuj dane konfiguracji ze środowiskiem finansów.
