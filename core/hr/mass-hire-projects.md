---
title: Projekty zatrudnienia grupowego
description: "Projekty zatrudnienia grupowego umożliwiają specjalistom z działów kadr tworzenie wielu stanowisk i sprawne rekrutowanie na nie pracowników."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMMassHireProject
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 006a8c110fe694c487e1e89e52c07438cf2becc3
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Projekty zatrudnienia grupowego
<a id="mass-hire-projects" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Projekty zatrudnienia grupowego umożliwiają specjalistom z działów kadr tworzenie wielu stanowisk i sprawne rekrutowanie na nie pracowników.

Przegląd
<a id="overview" class="xliff"></a>
--------

Użyj projektów zatrudnienia grupowego do jednoczesnego zatrudnienia kilku pracowników, np. kiedy zatrudniasz pracowników sezonowych. Tworzenie projektu zatrudnienia grupowego jest przydatne, ponieważ umożliwia jednoczesne tworzenie rekordów stanowisk, pracowników i przypisań pracowników. Podczas tworzenia stanowisk dla projektu zatrudnienia grupowego można określić następujące informacje:
-   Liczba stanowisk do utworzenia
-   Typ pracownika osób, które zostaną zatrudnione na tych stanowiskach
-   Dział i zadanie związane z tymi stanowiskami
-   Wartość przeliczenia na pełne etaty dla stanowiska

## Przykład
<a id="example" class="xliff"></a>
Latem zazwyczaj zatrudnia się 15-20 studentów na staże dostępne w firmie. W tym roku chcesz zatrudnić 5 księgowych, 5 osób do przetwarzania zamówień i 5 kasjerów. Zamiast tworzyć każdy rekord stanowiska i pracownika z osobna można utworzyć jeden projekt zatrudnienia grupowego pod nazwą „Letnistaż”. Daty rozpoczęcia i zakończenia projektu pokrywają się z datami rozpoczęcia i zakończenia ważności stanowisk utworzonych w ramach projektu zatrudnienia grupowego. 

Na stronie **Projekty zatrudnienia grupowego** wybierz projekt „Letnistaż” i kliknij **Otwórz projekt**. Na stronie Otwórz projekt zatrudnienia grupowego kliknij przycisk **Utwórz stanowiska** i wprowadź informacje o stanowisku księgowego. Można wybrać utworzenie pięciu stanowisk księgowych przy użyciu tych samych informacji, a następnie kliknąć przycisk OK. Powtórz ten proces dla stanowisk przetwarzania zamówień i kasjerów. 

Po wybraniu studentów, których chcesz przyjąć na staż wpisz dane każdego z nich na stronie **Szczegóły dotyczące stanowiska** dla stanowisk, na których mają zostać zatrudnieni. Po wprowadzeniu wszystkich szczegółów dotyczących stanowiska wybierz stanowisko na stronie Projekty zatrudnienia grupowego, a następnie kliknij **Zatrudnij**. Zostaną utworzone rekordy dla każdego stanowiska i pracownika, a każdy pracownik zostanie przypisany do odpowiedniego stanowiska.

## Stany projektu zatrudnienia grupowego
<a id="mass-hire-project-statuses" class="xliff"></a>
Projekt zatrudnienia grupowego może mieć następujące stany:
-   Utworzony
-   Otwarto
-   Zamknięto

Na stronie **projektu zatrudnienia grupowego** kliknij **Otwórz projekt** lub **Zamknij projekt**, aby zmienić stan projektu zatrudnienia grupowego. W poniższej tabeli opisano możliwości obsługi projektu w zależności od jego stanu.

<table>
<thead>
<tr class="header">
<th>Stan</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utworzony</td>
<td>Dla takiego projektu można tworzyć i modyfikować informacje, ale nie można tworzyć stanowisk. Jest to domyślny stan nowych projektów.</td>
</tr>
<tr class="even">
<td>Otwarto</td>
<td>Można modyfikować szczegóły projektu, tworzyć stanowiska projektu zatrudnienia grupowego i zatrudniać na nie. Jest to stan aktywnych projektów.</td>
</tr>
<tr class="odd">
<td>Zamknięto</td>
<td>Nie można dodać stanowisk do projektu. Aby dodać stanowiska do projektu zatrudnienia grupowego, otwórz ponownie projekt. Jest to stan zakończonych projektów.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Uwaga </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aby było możliwe zamknięcie projektu zatrudnienia grupowego, wszystkie stanowiska w projekcie muszą mieć stan Utworzono lub Zamknięto.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
</tbody>
</table>

 





