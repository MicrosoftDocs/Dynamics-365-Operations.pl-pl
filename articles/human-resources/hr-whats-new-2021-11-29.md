---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources, 19 listopada 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu samodzielnym Microsoft Dynamics 365 Human Resources w dniu 19 listopada 2021 roku.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 618d90f95637002f444b334e16d3fef466dda65e
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087481"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources, 19 listopada 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem aplikacji Dynamics 365 Human Resources 2021 — wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

W tej wersji uwzględniono następujące poprawki błędów. Zmiany dotyczą kompilacji o numerze 8.1.4591.

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Problem | Opis |
|---|---|---|
| 626178 | Brak nawigacji w kafelkach pracownika w obszarze **samoobsługi menedżera** | Ten problem został rozwiązany. Nawigacja jest dostępna, aby zobaczyć szczegóły raportu w obszarze **samoobsługi menedżera**. |
| 632573 | Nie ma żadnego błędu weryfikacji podczas zapisywania **kursu** | Ten problem został rozwiązany. Podczas tworzenia kursu z **minimalną liczbą uczestników** większą niż 0 nadal można było zapisać, nawet jeśli **maksymalna liczba uczestników** wynosi 0. |
| 615955 | Błąd „Pole **Cel** musi być wypełnione” podczas tworzenia nowej lokalizacji wniosku o rekrutację. | Podczas tworzenia adresu dla nowej lokalizacji zlecenia rekrutacji pojawia się błąd: „Pole „Cel” musi być wypełnione”. Pole **Cel** nie jest jednak dostępne na stronie. |
| 620797 | Błąd pustego pola **Płeć** jest mylący | Jeśli dla kontaktu osobistego nie wprowadzono płci, w raporcie jest wyświetlany tekst „Kliknij lub naciśnij tutaj, aby wprowadzić tekst” — jest to nieprawdziwe, ponieważ w tym polu nie można wprowadzać żadnych danych. |
| 620800 | Link do zestawienia świadczeń jest ukryty | W aplikacji **Samoobsługa pracownika etatowego** nie można domyślnie wyświetlać zestawienia świadczeń.  Do prawej strony obszaru **Samoobsługa pracownika etatowego** w sekcji **Linki** |
| 629778 | Problem z wydajnością integracji z usługą CDS. | Żądanie autoryzacji spowodowało problem z wydajnością. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub wyłączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Wkrótce
Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2021 r.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
