---
title: Generowanie raportów poprzez dodawanie treści w postaci nieprzetworzonego kodu XML
description: Można zaprojektować formaty raportów elektronicznych ER, które wygenerują wychodzące dokumenty w formacie XML.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 3e007b4feac612ecf74f60dd8a87d76efc7ab4c7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752799"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]