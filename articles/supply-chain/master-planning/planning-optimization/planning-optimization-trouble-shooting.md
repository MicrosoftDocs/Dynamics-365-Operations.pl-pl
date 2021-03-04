---
title: Rozwiązywanie problemów z optymalizacją planowania
description: W tym temacie opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z optymalizacją planowania.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: c3dd0bf262f65aac2359c05ff954bdfbd294353f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435003"
---
# <a name="troubleshoot-planning-optimization"></a>Rozwiązywanie problemów z optymalizacją planowania 

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób rozwiązywania typowych problemów, które mogą wystąpić podczas pracy z optymalizacją planowania.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>Nie zakończono instalacji dodatku Optymalizacja planowania

Optymalizacja planowania wymaga środowiska wysokiej dostępności z włączonymi usługami Lifecycle Services (LCS) w warstwie 2 lub wyższej (a nie środowiska OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej. Jeśli spróbujesz zainstalować dodatek w środowisku OneBox, instalacja nie zostanie zakończona.

**Poprawka** : anuluj instalację i użyj środowiska wysokiej dostępności w warstwie 2 lub wyższej (a nie środowiska Onebox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>Planowanie zadań wsadowych kończy się niepowodzeniem po włączeniu optymalizacji planowania

Po włączeniu optymalizacji planowania wbudowany aparat planowania głównego jest automatycznie wyłączany. Zadania wsadowe planowania głównego utworzone dla wbudowanego aparatu planowania Supply Chain Management dostaw zakończą się niepowodzeniem, jeśli będą wyzwalane po włączeniu optymalizacji planowania. Może zostać wyświetlony komunikat o błędzie, taki jak *Ta operacja wyzwoliła planowanie główne, które nie jest obsługiwane po włączeniu optymalizacji planowania*.

**Poprawka** : anuluj wszystkie zadania wsadowe planowania głównego, które zostały utworzone dla wbudowanego aparatu Supply Chain Management.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Wyniki optymalizacji planowania różnią się od poprzednich wyników

Optymalizacja planowania różni się od wbudowanego projektu planowania głównego w niektórych obszarach. Może to być również spowodowane przez oczekujące funkcje.

**Poprawka**: uruchom analizę dopasowania optymalizacji planowania i przeanalizuj wyniki, używając odpowiedniej dokumentacji w celu zrozumienia ich wpływu. Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).

## <a name="master-planning-doesnt-respect-the-coverage-time-fence"></a>Planowanie główne nie uwzględnia horyzontu czasowego zapotrzebowania

Jest to spowodowane przez funkcję oczekującą dla optymalizacji planowania.

**Poprawka** : do momentu udostępnienia funkcji oczekującej można filtrować lub usuwać zamówienia planowane w celu usunięcia sugestii dotyczących dostaw poza horyzontem czasowym zapotrzebowania.

## <a name="cant-enable-planning-optimization"></a>Nie można włączyć optymalizacji planowania

**Stan połączenia** musi być mieć wartość **Połączono**, aby można było ustawić opcję **Użyj optymalizacji planowania** na **Tak**. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z optymalizacją planowania](get-started.md).

**Poprawka**: upewnij się, że dodatek Optymalizacja planowania został pomyślnie zainstalowany.

## <a name="error-message-is-shown-during-ctp"></a>Komunikat o błędzie jest wyświetlany podczas CTP

W przypadku próby uruchomienia operacji „możliwe do zrealizowania” (CTP) z zamówienia sprzedaży, gdy jest włączona optymalizacja planowania, zostanie wyświetlony następujący komunikat o błędzie: *Ta operacja wyzwoliła planowanie główne, które nie jest obsługiwane po włączeniu optymalizacji planowania*.

Jest to związane z oczekującą funkcją, która jest planowana jako część obsługi zleceń produkcyjnych.

**Poprawka:** unikaj obliczeń CTP po włączeniu optymalizacji planowania, dopóki nie będzie dostępna obsługa CTP.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Rozpoczęcie optymalizacji planowania](get-started.md)

[Analiza dopasowań optymalizacji planowania](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]