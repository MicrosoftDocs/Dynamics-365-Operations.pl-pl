---
title: Rozwiązywanie problemów z optymalizacją planowania
description: W tym artykule opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z optymalizacją planowania.
author: t-benebo
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 37c38ab9cec8ae3c9d4decf8043b43ea2251083e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739737"
---
# <a name="troubleshoot-planning-optimization"></a>Rozwiązywanie problemów z optymalizacją planowania 

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób rozwiązywania typowych problemów, które mogą wystąpić podczas pracy z optymalizacją planowania.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>Nie zakończono instalacji dodatku Optymalizacja planowania

Optymalizacja planowania wymaga środowiska wysokiej dostępności z włączonymi usługami Lifecycle Services (LCS) w warstwie 2 lub wyższej (a nie środowiska OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej. Jeśli spróbujesz zainstalować dodatek w środowisku OneBox, instalacja nie zostanie zakończona.

**Poprawka** : anuluj instalację i użyj środowiska wysokiej dostępności w warstwie 2 lub wyższej (a nie środowiska Onebox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>Planowanie zadań wsadowych kończy się niepowodzeniem po włączeniu optymalizacji planowania

Po włączeniu optymalizacji planowania przestarzały aparat planowania głównego jest automatycznie wyłączany. Zadania wsadowe planowania głównego utworzone dla przestarzałego aparatu planowania głównego dostaw zakończą się niepowodzeniem, jeśli będą wyzwalane po włączeniu optymalizacji planowania. Może zostać wyświetlony komunikat o błędzie, taki jak *Ta operacja wyzwoliła planowanie główne, które nie jest obsługiwane po włączeniu optymalizacji planowania*.

**Poprawka** : anuluj wszystkie zadania wsadowe planowania głównego, które zostały utworzone dla przestarzałego aparatu planowania głównego.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Wyniki optymalizacji planowania różnią się od poprzednich wyników

Optymalizacja planowania różni się od przestarzałego aparatu planowania głównego w niektórych obszarach. Może to być również spowodowane przez oczekujące funkcje.

**Poprawka**: uruchom analizę dopasowania optymalizacji planowania i przeanalizuj wyniki, używając odpowiedniej dokumentacji w celu zrozumienia ich wpływu. Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>Nie można włączyć optymalizacji planowania

**Stan połączenia** musi być mieć wartość **Połączono**, aby można było ustawić opcję **Użyj optymalizacji planowania** na **Tak**. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z optymalizacją planowania](get-started.md).

**Poprawka**: upewnij się, że dodatek Optymalizacja planowania został pomyślnie zainstalowany.

## <a name="error-message-is-shown-during-ctp"></a>Komunikat o błędzie jest wyświetlany podczas CTP

W przypadku próby uruchomienia operacji „możliwe do zrealizowania” (CTP) z zamówienia sprzedaży, gdy jest włączona optymalizacja planowania, zostanie wyświetlony następujący komunikat o błędzie: *Ta operacja wyzwoliła planowanie główne, które nie jest obsługiwane po włączeniu optymalizacji planowania*.

Jest to związane z oczekującą funkcją, która jest planowana jako część obsługi zleceń produkcyjnych.

**Poprawka:** unikaj obliczeń CTP po włączeniu optymalizacji planowania, dopóki nie będzie dostępna obsługa CTP.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Rozpoczęcie pracy z planowaniem głównym](get-started.md)
- [Analiza dopasowań optymalizacji planowania](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]