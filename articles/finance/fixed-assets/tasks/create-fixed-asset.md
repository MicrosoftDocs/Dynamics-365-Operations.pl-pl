---
title: Tworzenie środka trwałego
description: W tym artykule opisano sposób tworzenia nowego rekordu środka trwałego na stronie listy środków trwałych.
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00c72081d20015737aa027cee9474a54e498cef4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868497"
---
# <a name="create-a-fixed-asset"></a>Tworzenie środka trwałego

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób tworzenia nowego rekordu środka trwałego na stronie listy **środków trwałych**.

System przypisuje numer środka trwałego na podstawie sekwencji numerów przypisanej do grupy środków trwałych. Jeśli do importowania środków trwałych za pomocą dodatku Microsoft Excel używany jest szablon środków trwałych lub zostanie użyte inne zadanie importowania, system automatycznie utworzy rekordy środków trwałych i zwiększy numer środka trwałego.

Aby ręcznie utworzyć rekord środka trwałego, należy wykonać następujące kroki.

1. Otwórz **Okienko nawigacji \> Moduły \> Środki trwałe \> Środki trwałe \> Środki trwałe**.
2. W **Okienku akcji** wybierz opcję **Nowy**.
3. W polu **Grupa środków trwałych** wprowadź lub wybierz wartość. Wartość w polu **Numer** będzie ustawiana domyślnie, jeśli włączono **funkcję Automatyczna numeracja środków trwałych** w oknie **Parametry środków trwałych** oraz włączono funkcję **Grupa środków trwałych**. Jeśli nie, samodzielnie wprowadź unikatowy numer identyfikujący środek trwały.
4. Wprowadź wartość w polu **Nazwa**. Wprowadź dodatkowe informacje, jakich firma potrzebuje o tym składniku aktywów.
5. W **Okienku akcji** wybierz pozycję **Księgi**.
6. W polu **Data nabycia** wprowadź datę.
7. W polu **Cena nabycia** wpisz liczbę.

    - Wprowadź dodatkowe informacje, jakich firma potrzebuje o tej księdze.
    - Wprowadź dodatkowe informacje, jakich firma potrzebuje o pozostałych księgach.

8. Zamknij stronę.

Środki trwałe można również zaimportować za pomocą dodatku programu Excel lub uruchamiając zadanie importu z obszaru roboczego **Zarządzanie danymi**. Przed uruchomieniem importu należy wprowadzić wartości wymaganych pól w szablonie.

Jeśli nie zdefiniowano numeru środka trwałego w szablonie dodatku programu Excel lub w module Zarządzanie danymi, system utworzy numer środka trwałego dla każdego importowanego środka trwałego i automatycznie zwiększy sekwencję numerów dla każdego z nich. Jednak w przypadku importowania środków trwałych i definiowania numerów środków w szablonie system **nie** zwiększa automatycznie sekwencji numerów. W takim przypadku administrator może ręcznie zaktualizować sekwencję numerów. Jeśli zdefiniowano numer środka trwałego w szablonie dodatku Excel, system używa zdefiniowanego numeru środka trwałego i zwiększa sekwencję numerów.

> [!NOTE]                                                                                                         
> Po zaksięgowaniu amortyzacji pola **Rozpoczęcie eksploatacji** i **Data rozpoczęcia amortyzacji** zostaną zablokowane na stronie **Księga**. Ponadto oba pola nie zostaną zaktualizowane na podstawie jednostki danych.

> [!WARNING]
> Rekord środka trwałego nie zostanie usunięty, jeśli transakcje zostały zaksięgowane w skojarzonej księdze, lub jeśli nowo utworzony środek trwały został wprowadzony w wierszu arkusza, ale nie zostanie zaksięgowany. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
