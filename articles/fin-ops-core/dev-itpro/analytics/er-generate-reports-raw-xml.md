---
title: Generowanie raportów poprzez dodawanie treści w postaci nieprzetworzonego kodu XML
description: Można zaprojektować formaty raportów elektronicznych ER, które wygenerują wychodzące dokumenty w formacie XML.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 21449b8684256c5ddf6d710175b3724c300da428
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181411"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Generowanie raportów poprzez dodawanie treści w postaci nieprzetworzonego kodu XML

[!include[banner](../includes/banner.md)]

Można użyć nowego elementu formatu **RAW XML** do zaprojektowania formatów Raportowania elektronicznego (ER), które wygenerują wychodzące dokumenty w formacie XML. W niektórych przypadkach warto dodać do tych raportów nieprzetworzone dane XML dla jednego lub kilku poniższych powodów:

- Wygodniej jest używać nieprzetworzonego kodu XML w oryginalnym projekcie i bieżącej konserwacji raportu, ponieważ struktura ML może być generowana automatycznie poprzez uruchomienie wyrażenia czasu wykonywania. W związku z tym w czasie projektowania nie trzeba ustalać wielu powiązań dla wielu elementów formatu. Jest to możliwe, gdy używane źródła danych zawierają informacje, których można użyć do tworzenia elementów XML podczas generowania raportu.
- Żadna inna metoda nie może służyć do wypełniania raportu zawartością XML, którą uprzednio otrzymano i zapisano w systemie. Na przykład może istnieć wymóg, aby generowana odpowiedź XML zawierała treść wysłanego wcześniej żądania XML.
- Żadnej innej metody nie można używać do wstawiania znaków do wygenerowanego dokumentu na podstawie ich kodów numerycznych. Dla niektórych języków i znaków kody tego typu nie istnieją. Przykładami są grecka literę (ρ) i kody obiektów HTML, takie jak \&eacute; dla *e*, która ma znak akcentu ostrego (é).

> [!NOTE]
> Należy pamiętać, że struktura nie kontroluje, czy zawartości XML umieszczana w wygenerowanym dokumencie za pomocą elementu formatu **RAW XML**, jest poprawna.

Aby dowiedzieć się więcej o tej funkcji, należy odtworzyć przewodniki po zadaniach **Użycie nieprzetworzonych danych XML do generowania raportów XML (część 1: model danych)** i **Użycie nieprzetworzonych danych XML do generowania raportów XML (część 2: projektowanie i tworzenie raportów)**, które są częścią procesu biznesowego **7.5.4.3 Pobieranie/opracowywanie składników usług/rozwiązań informatycznych (10677)** i można je pobrać z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Te wskazówki zadania przeprowadzą Cię przez proces konfigurowania formatu ER w celu wstawienia nieprzetworzonych danych XML do wygenerowanych plików.
