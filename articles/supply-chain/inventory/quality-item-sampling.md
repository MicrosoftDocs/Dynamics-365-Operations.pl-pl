---
title: Kontrola wyrywkowa towaru zarządzania jakością
description: W tym artykule opisano sposób konfigurowania kontroli wyrywkowej towaru.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 644eae4fbd9f82027c1cb69efba00dc893f8fc66
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865158"
---
# <a name="quality-management-item-sampling"></a>Kontrola wyrywkowa towaru zarządzania jakością

[!include [banner](../includes/banner.md)]

Kontrola wyrywkowa towaru jest używana jako część skojarzenia jakości. Określa ona ilość bieżących zapasów fizycznych, które muszą zostać sprawdzone. Kontrola wyrywkowa może dotyczyć stałej ilości lub części określonej procentowo lub pełnego numeru identyfikacyjnego.

## <a name="set-up-item-sampling"></a>Konfigurowanie wyrywkowej kontroli towarów

Wykonaj następujące czynności, aby skonfigurować kontrolę wyrywkową towarów.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Kontrola wyrywkowa towarów**.
1. Wybierz pozycję **Nowy**.
1. W polu **Kontrola wyrywkowa towarów** wpisz wartość.
1. W polu **Opis** wprowadź lub wybierz wartość.
1. W polu **Wartość** wprowadź liczbę. Ta wartość odnosi się do wartości specyfikacji ilości wybranej w sąsiednim polu.
1. W sekcji **Proces** zaznacz pole wyboru **Pełne blokowanie**, jeśli w przypadku niezaliczonych testów ma być zablokowana cała ilość w wierszu zamówienia lub partii. Jeśli to pole wyboru nie jest zaznaczone, w przypadku niezaliczonych testów tylko towary w zleceniu kontroli jakości zostaną zablokowane.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę.

> [!NOTE]
> Funkcja *Zarządzania jakością dla procesów magazynowych* dodaje nowe możliwości wyrywkowej kontroli towaru. Dodaje pojęcie *Zakres kontroli wyrywkowej towarów* i umożliwia zdefiniowanie pełnego numeru identyfikacyjnego jako specyfikacji ilości. Jeśli ta funkcja została włączona, zobacz temat [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
