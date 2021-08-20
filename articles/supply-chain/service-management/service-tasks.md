---
title: Omówienie zadań serwisowych
description: Zadania serwisowe służą do opisywania zadań, które mają zostać wykonane podczas zlecenia serwisowego. Te informacje są widoczne zarówno dla techników, jak i klientów.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d981972fcdc75de5504ba3341f4ed2cf8f971cb2d13037fd88f01a720cd1cc60
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782426"
---
# <a name="service-tasks-overview"></a>Omówienie zadań serwisowych

[!include [banner](../includes/banner.md)]

Zadania serwisowe służą do opisywania zadań, które mają zostać wykonane podczas zlecenia serwisowego.
Te informacje są widoczne zarówno dla techników, jak i klientów.

Zadania serwisowe tworzy się na stronie **Zadania serwisowe** i kojarzy z określoną umową serwisową lub zleceniem serwisowym przez utworzenie relacji zadania serwisowego. Przy każdym tworzeniu relacji zadania serwisowego można utworzyć następujące obiekty:

-  Wewnętrzne notatki dotyczące zadania, na przykład szczegółowe wymagania techniczne dotyczące zadania, których znajomość jest istotna dla techników.

-  Zewnętrzne notatki widoczne dla klienta. Mogą one zawierać mniej techniczne objaśnienie zadania, które jest wykonywane zgodnie z umową między klientem a firma serwisową.

Po skonfigurowaniu relacji między zadaniem serwisowym a zleceniem serwisowym lub umową serwisową można określić to zadanie serwisowe podczas tworzenia wierszy zlecenia serwisowego lub wierszy umowy serwisowej dla bieżącego zlecenia serwisowego lub umowy serwisowej.

Podczas generowania zleceń serwisowych z umowy serwisowej można używać zadań serwisowych przypisanych do poszczególnych wierszy umowy serwisowej w celu grupowania wierszy zlecenia serwisowego w zlecenia serwisowe.

## <a name="create-a-service-task"></a>Tworzenie zadania serwisowego

1. Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zadania serwisowe**.
2. Utwórz nowy wiersz.
3. Wprowadź identyfikator i opis usługi.

## <a name="example"></a>Przykład

Technik musi wykonać dwie prace związane ze skrzynią biegów (przedmiot serwisu GB-1234) na miejscu u klienta. Dla klienta zostaje utworzona umowa serwisowa, a z pracami zostaje skojarzonych klika transakcji. Oto umowa serwisowa i wiersze umowy serwisowej dotyczące tych dwóch prac:

### <a name="service-agreement"></a>Umowa serwisowa

| Project | Umowa serwisowa | opis                                  | Grupa   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Przegląd i rutynowa wymiana — GB-1234 | Premia |

### <a name="service-agreement-lines"></a>Wiersze umowy serwisowej

| opis             | Typ transakcji | Przedmiot serwisu | Zadanie serwisowe |
|-------------------------|------------------|----------------|--------------|
| Przegląd i oczyszczenie | Godzina             | GB-1234        | I/C - GB1234 |
| Podróże                  | Expense          | GB-1234        | I/C - GB1234 |
| Materiały               | Element             | GB-1234        | I/C - GB1234 |
| Rutynowa wymiana     | Godzina             | GB-1234        | RR - GB1234  |
| GR-1                    | Element             | GB-1234        | RR - GB1234  |
| GR-5                    | Element             | GB-1234        | RR - GB1234  |

W wierszach umowy serwisowej dla tych dwóch prac są określone dwa zadania serwisowe. Zadania serwisowe określają transakcje, które należą do każdej pracy. W pierwszym przypadku zadanie serwisowe I/C - GB1234 określa wszystkie wiersze umowy serwisowej związane z przeglądem i oczyszczeniem przedmiotu GB-1234. W drugim przypadku zadanie serwisowe RR - GB1234 określa wszystkie wiersze umowy serwisowej związane z przeprowadzeniem rutynowej wymiany.

Relacje zadań serwisowych łączące zadania serwisowe z określoną umową są następujące:

### <a name="service-tasks"></a>Zadania serwisowe

| Zadanie serwisowe | Opis                             | Notatka wewnętrzna                                                                                                                 | Notatka zewnętrzna                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | Przegląd skrzyni biegów GB-1234           | Wzrokowy i mechaniczny przegląd oraz oczyszczenie skrzyni biegów GB-1234                                                              | Rutynowy przegląd skrzyni biegów |
| RR - GB1234  | Rutynowa wymiana części w skrzyni biegów GB-1234 | Rutynowa wymiana części GR-1 i GR-5 (skrzyń biegów wyprodukowanych przed 2002 rokiem dotyczy również wymiana części GR-2) | Rutynowa wymiana części  |

## <a name="group-service-orders"></a>Grupowanie zleceń serwisowych

W przypadku automatycznego tworzenia zleceń serwisowych zadania serwisowe mogą służyć jako kryteria grupowania. Aby pogrupować zlecenia serwisowe według zadań serwisowych, należy określić w umowie serwisowej, że oparte na niej zlecenia serwisowe powinny być grupowane najpierw według identyfikatorów zadań serwisowych.

**Grupowanie według zadań serwisowych**

1. Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.
2. Na karcie **Ustawienia** w polu **Łączenie zleceń serwisowych** wybierz opcję **Według zadania serwisowego**.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]