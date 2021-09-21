---
title: Ostrzeżenia lub błędy dotyczące zmiany stanu okresu księgi bez zamykania magazynu
description: Ostrzeżenia lub błędy dotyczące zmiany stanu okresu księgi bez zamykania magazynu
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477294"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Ostrzeżenia lub błędy dotyczące zmiany stanu okresu księgi bez zamykania magazynu

Firma Microsoft wprowadziła następujące procesy weryfikacji, aby zapobiec problemom spowodowanym przez nieprawidłowy proces zakończenia okresu dotyczący kalkulacji kosztów. W przypadku napotkania dowolnego z poniższych komunikatów o błędach zapoznaj się z [4561987 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3), aby uzyskać więcej informacji dotyczących sposobu rozwiązywania tych problemów.

- Zamierzasz wykonać ponowne obliczenie z datą %1 (10-02-2019). Ostatnie zarejestrowane ponowne obliczenie zostało wykonane w poprzednim okresie z datą %2 (20-01-2019). Nie zarejestrowano wykonania zamknięcia zapasów z datą %3 (31-01-2019) końca okresu dopasowania. Należy pamiętać o wykonaniu zamknięcia zapasów w dacie %3 (31-01-2019), odpowiadającej zakończeniu okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

- Zamierzasz zmienić stan okresu księgi %1 na %2. Nie zarejestrowano wykonania zamknięcia zapasów z datą %3, odpowiadającą zakończeniu okresu. Przed zmianą statusu należy wykonać zamknięcie zapasów na %3 odpowiadające końcowi okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji. Zgłoszone przez firmę %4. Obecnie ta akcja ma wartość informacyjną, ale w przyszłości jej wykonanie będzie wymagane.

- Struktura konta %1 została zmieniona. Co najmniej jedno konto główne %2 już nie istnieje. Te konta główne są wymagane przez %3 z datą %4. Dodaj te konta główne do struktury konta %1, aby móc wznowić zadanie %3. Obecnie ta akcja ma wartość informacyjną, ale w przyszłości jej wykonanie będzie wymagane.

- Zamierzasz wykonać zamknięcie zapasów z datą %1 (31-01-2019). Nie zarejestrowano wykonania obliczania wyceny wstecznej z datą %2 (31-01-2019) pasującą do zakończenia okresu. Należy pamiętać o wykonaniu obliczania wyceny wstecznej z datą %3 (31-01-2019) pasującą do zakończenia okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

- Zamierzasz wykonać obliczenie wycent wstecznej z datą %1 (28-02-2019). Ostatnie zarejestrowane obliczenie wyceny wstecznej zostało wykonane w poprzednim okresie z datą %2 (31-01-2019). Nie zarejestrowano wykonania zamknięcia zapasów z datą %3 (31-01-2019) końca okresu dopasowania.

Należy pamiętać o wykonaniu zamknięcia zapasów w dacie %3 (31-01-2019), odpowiadającej zakończeniu okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do wykonania zamknięcia zapasów.