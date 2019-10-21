---
title: Parametry integracji aplikacji Project Service Automation
description: W tym temacie wyjaśniono, jak skonfigurować sposób wprowadzania domyślnych danych podczas integrowania Microsoft Dynamics 365 for Project Service Automation z Microsoft Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: f7cef5384812e0dcb7d5e084ddd7668a7687a259
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174993"
---
# <a name="project-service-automation-integration-parameters"></a>Parametry integracji z rozwiązaniem Project Service Automation

[!include[banner](../includes/banner.md)]

Na stronie **Parametry integracji aplikacji Project Service Automation** można skonfigurować sposób wprowadzania domyślnych danych podczas integrowania programu Dynamics 365 Project Service Automation z programem Dynamics 365 Finance. W celu pomyślnej synchronizacji projektów z rozwiązania Project Service Automation do rozwiązania Finance należy skonfigurować następujące pola:

> [!NOTE]
> - Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w wersji 8.0.
> - Funkcja integrowania wartości rzeczywistych jest dostępna wersji 8.01 i nowszych.


| Tab                    | Pole                | Opis |
|------------------------|----------------------|-------------|
| Ogólne                | Domyślny typ projektu | Umożliwia wybór domyślnego typu projektu. Podczas synchronizowania projektów z aplikacji Project Service Automation ta wartość jest używana, jeśli nie podano wartości domyślnej w szablonie integracji. Podczas synchronizacji pole **Typ projektu** w nowych projektach otrzymuje tę wartość. Jednak wartość może być aktualizowana, gdy wiersze umowy na projekt są synchronizowane z aplikacji Project Service Automation. |
|                        | Kategoria czasu        | Umożliwia wybór domyślnej kategorii czasu. Ta wartość jest używana podczas synchronizowania szacunków godzinowych z aplikacji Project Service Automation. Gdy wartości szacowane i rzeczywiste godzin są synchronizowane z modułu Project Service Automation, pole **Kategoria** w nowych prognozach godzin w projekcie w programie Finance otrzyma tę wartość. |
|                        | Kategoria opłat         | Umożliwia wybór domyślnej kategorii opłat. Ta wartość jest używana podczas synchronizowania rzeczywistych wartości opłat z aplikacji Project Service Automation. Gdy wartości rzeczywiste opłat są synchronizowane z modułu Project Service Automation, pole **Kategoria** w nowych transakcjach opłat w programie Finance otrzyma tę wartość. |
| Wartości domyślne grupy projektów | Typ projektu         | Kliknij przycisk **Nowy** i dodaj wiersz, w którym będzie można wybrać typ projektu, dla którego będzie ustawiana domyślna grupa projektu. Konkretny typ projektu można wybrać tylko raz w konfiguracji. |
|                        | Grupa projektów        | Wybierz domyślną grupa projektów dla podanego typu projektu. Kiedy nowe projekty są synchronizowane z aplikacji Project Service Automation, pole **Grupa projektów** otrzyma wartość domyślną dla typu projektu, jeśli nie podano wartości domyślnej w szablonie integracji. |
| Ustawienia domyślne typu fakturowania  | Typ fakturowania         | Kliknij przycisk **Nowy** i dodaj wiersz, w którym będzie można wybrać typ fakturowania, dla którego będzie ustawiana domyślna właściwość wiersza. Konkretny typ fakturowania można wybrać tylko raz w konfiguracji. |
|                        | Właściwość wiersza        | Wybierz domyślną właściwość wiersza dla podanego typu fakturowania. Gdy nowe szacunki godzinowe, nowe szacunki wydatków lub nowe wartości rzeczywiste są synchronizowane z aplikacji Project Service Automation, pole **Właściwość wiersza** otrzymuje wartość domyślną dla typu fakturowania. |
| Blokowanie funkcji  | Nie dotyczy       | Wybierz funkcje, które w programie Finance mają zostać wyłączone dla projektów i umów pochodzących z modułu Project Service Automation. Na przykład można wyłączyć możliwość edytowania umów i projektów, tworzyć struktury podziału pracy oraz wypełniać kart czasu pracy w programie Finance. Pola związane z księgowaniem nadal będą włączone, nawet jeśli ustawienie parametru spowodowało, że są niedostępne. Domyślnie wszystkie funkcje są włączone. |
