---
title: Projekty zatrudnienia grupowego
description: Projekty zatrudnienia grupowego umożliwiają specjalistom z działów kadr tworzenie wielu stanowisk i sprawne rekrutowanie na nie pracowników.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f33fb96e9a2331499a594689a758694c2291368
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420086"
---
# <a name="mass-hire-projects"></a>Projekty zatrudnienia grupowego



Projekty zatrudnienia grupowego umożliwiają specjalistom z działów kadr tworzenie wielu stanowisk i sprawne rekrutowanie na nie pracowników.

## <a name="overview"></a>Przegląd

Użyj projektów zatrudnienia grupowego do jednoczesnego zatrudnienia kilku pracowników, np. kiedy zatrudniasz pracowników sezonowych. Tworzenie projektu zatrudnienia grupowego jest przydatne, ponieważ umożliwia jednoczesne tworzenie rekordów stanowisk, pracowników i przypisań pracowników. Podczas tworzenia stanowisk dla projektu zatrudnienia grupowego można określić następujące informacje:

- Liczba stanowisk do utworzenia
- Typ pracownika osób, które zostaną zatrudnione na tych stanowiskach
- Dział i zadanie związane z tymi stanowiskami
- Wartość przeliczenia na pełne etaty dla stanowiska

## <a name="example"></a>Przykład

Latem zazwyczaj zatrudnia się 15-20 studentów na staże dostępne w firmie. W tym roku chcesz zatrudnić 5 księgowych, 5 osób do przetwarzania zamówień i 5 kasjerów. Zamiast tworzyć każdy rekord stanowiska i pracownika z osobna można utworzyć jeden projekt zatrudnienia grupowego pod nazwą „Letnistaż”. Daty rozpoczęcia i zakończenia projektu pokrywają się z datami rozpoczęcia i zakończenia ważności stanowisk utworzonych w ramach projektu zatrudnienia grupowego.

Na stronie **Projekty zatrudnienia grupowego** wybierz projekt „Letnistaż” i kliknij **Otwórz projekt**. Na stronie Otwórz projekt zatrudnienia grupowego kliknij przycisk **Utwórz stanowiska** i wprowadź informacje o stanowisku księgowego. Można wybrać utworzenie pięciu stanowisk księgowych przy użyciu tych samych informacji, a następnie kliknąć przycisk OK. Powtórz ten proces dla stanowisk przetwarzania zamówień i kasjerów.

Po wybraniu studentów, których chcesz przyjąć na staż wpisz dane każdego z nich na stronie **Szczegóły dotyczące stanowiska** dla stanowisk, na których mają zostać zatrudnieni. Po wprowadzeniu wszystkich szczegółów dotyczących stanowiska wybierz stanowisko na stronie Projekty zatrudnienia grupowego, a następnie kliknij **Zatrudnij**. Zostaną utworzone rekordy dla każdego stanowiska i pracownika, a każdy pracownik zostanie przypisany do odpowiedniego stanowiska.

## <a name="mass-hire-project-statuses"></a>Stany projektu zatrudnienia grupowego

Projekt zatrudnienia grupowego może mieć następujące stany:

- Utworzony
- Otwarto
- Zamknięto

Na stronie **projektu zatrudnienia grupowego** kliknij **Otwórz projekt** lub **Zamknij projekt**, aby zmienić stan projektu zatrudnienia grupowego. W poniższej tabeli opisano możliwości obsługi projektu w zależności od jego stanu.

<table>
<thead>
<tr>
<th>Stan</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Utworzony</td>
<td>Dla takiego projektu można tworzyć i modyfikować informacje, ale nie można tworzyć stanowisk. Jest to domyślny stan nowych projektów.</td>
</tr>
<tr>
<td>Otwarto</td>
<td>Można modyfikować szczegóły projektu, tworzyć stanowiska projektu zatrudnienia grupowego i zatrudniać na nie. Jest to stan aktywnych projektów.</td>
</tr>
<tr>
<td>Zamknięto</td>
<td>Nie można dodać stanowisk do projektu. Aby dodać stanowiska do projektu zatrudnienia grupowego, otwórz ponownie projekt. Jest to stan zakończonych projektów.
<blockquote>[!NOTE] Aby było możliwe zamknięcie projektu zatrudnienia grupowego, wszystkie stanowiska w projekcie muszą mieć stan Utworzono lub Zamknięto.</blockquote>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]