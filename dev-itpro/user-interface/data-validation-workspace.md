---
title: "Obszar roboczy sprawdzania poprawności danych"
description: "Obszar roboczy Lista kontrolna weryfikacji danych umożliwia śledzenie procesów sprawdzania poprawności danych dla różnych firm, obszarów i osób. Lista kontrolna może być używana podczas nowej implementacji, po wykonaniu uaktualnienia lub po migracji."
author: bking
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: 
ms.assetid: 
ms.search.region: Global
ms.author: bking
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: e105c4b171979a03c20718c1fa9d558c921cd704
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Obszar roboczy sprawdzania poprawności danych
<a id="data-validation-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten temat zawiera omówienie obszaru roboczego **Lista kontrolna weryfikacji danych** oraz pokrewnej konfiguracji.

## Obszar roboczy Lista kontrolna weryfikacji danych
<a id="data-validation-checklist-workspace" class="xliff"></a>

Obszar roboczy **Lista kontrolna weryfikacji** danych umożliwia śledzenie procesów sprawdzania poprawności danych dla różnych firm, obszarów i osób. Lista kontrolna może być używana podczas nowej implementacji, po wykonaniu uaktualnienia lub po migracji. W zależności od widoku obszaru roboczego **Lista kontrolna weryfikacji danych** będą widoczne albo wszystkie zadania i stany dla projektu sprawdzania poprawności danych, albo tylko zadania, które są przypisane do Ciebie.

Należy najpierw wybrać projekt weryfikacji danych w górnej części obszaru roboczego. Wszystkie dane, które są widoczne w obszarze roboczym, są następnie filtrowane według wybranego projektu weryfikacji danych.

### Kafelki podsumowania
<a id="summary-tiles" class="xliff"></a>

Kafelki **Podsumowanie** oferują podgląd procesu, a wskaźniki pomagające utrzymać proces weryfikacji danych na odpowiednich torach. Widać wszystkie zadania pozostałe, zadania ukończone, zadania w toku i zadania jeszcze nie rozpoczęte w procesie. Te informacje dotyczą wszystkich firm, które są uwzględniane w wybranym projekcie weryfikacji danych.

### Sekcja Zadania i stan
<a id="tasks-and-status-section" class="xliff"></a>

W sekcji **Zadania i stan** stan całego projektu sprawdzania poprawności danych jest wyświetlany na różne sposoby: według firmy, obszaru i listy zadań. Można również wybrać filtr pokazujący stan dla określonego przedsiębiorstwa. Każda karta stanu pokazuje podział według procentu ukończenia oraz według liczby pozostałych zadań.

Na ostatniej karcie jest szczegółowa lista zadań. Ta lista pokazuje wszystkie zadania.
Listę zadań można filtrować na kilka sposobów. Kliknij przycisk **Edytuj zadanie**, aby zmienić stan zadania i lub przydzielić zadanie. Kliknij przycisk **Załączniki**, aby wyświetlić załączniki do zadania.

Nazwa zadania jest hiperłączem do strony programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, na którą użytkownik musi przejść, aby ukończyć pracę. To hiperłącze można ustawić przy użyciu pola **Nazwa elementu menu** podczas edytowania lub tworzenia zadania z formularza **Konfiguruj projekt weryfikacji danych**.

Do zadania można dołączać pliki, notatki, obrazy i adresy URL za pomocą akcji **Załączniki**. Na przykład można dołączyć plik raportu wydrukowanego dla zadania. Ikona pojawia się w kolumnie **Załącznik** dla zadania, jeśli załącznik jest obecny.

Opcja **Wykonane przez** jest automatycznie wypełniane po zakończeniu zadania imieniem i nazwiskiem pracownika, który wykonał zadanie. Gdy zadanie jest oznaczone jako ukończone, pole **Data zakończenia** jest automatycznie aktualizowane na bieżącą datę i godzinę.

### Strona Konfiguruj projekt weryfikacji danych
<a id="configure-data-validation-project-page" class="xliff"></a>

Aby można było używać obszaru roboczego **Lista kontrolna weryfikacji danych**, należy skonfigurować proces za pomocą strony **Konfiguruj projekt weryfikacji danych**. (Kliknij kolejno opcje **Obszary robocze** \> **Lista kontrolna weryfikacji danych** \> **Konfiguruj projekt weryfikacji danych**).

### Obszary zadań
<a id="task-areas" class="xliff"></a>

Za pomocą obszarów zadań można grupować zadania weryfikacji danych w logiczne obszary własności w obrębie organizacji. Obszarami zadań mogą być na przykład Rozrachunki z dostawcami, Rozrachunki z odbiorcami lub Księga główna.

Pole **Nazwa elementu menu** jest skojarzone z pracą w zadaniu i pozwala przejść bezpośrednio do skojarzonej strony z łącza zadania w obszarze roboczym. Na przykład zadanie weryfikacji danych polegające na wygenerowaniu raportu **Wiekowanie rozrachunków z dostawcami** dla modułu Rozrachunki z dostawcami może być połączone ze stroną **Raport o wiekowaniu rozrachunków z dostawcami** strony.

