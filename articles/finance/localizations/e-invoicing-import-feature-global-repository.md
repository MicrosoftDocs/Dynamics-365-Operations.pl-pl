---
title: Importowanie funkcji z repozytorium globalnego
description: W tym artykule opisano sposób importowania funkcji globalizacji z repozytorium globalnym.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5a72673e17c5653d43b60d3348d5518e09c40a15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278320"
---
# <a name="import-features-from-the-global-repository"></a>Importowanie funkcji z repozytorium globalnego

[!include [banner](../includes/banner.md)]

Repozytorium globalne zawiera funkcje fakturowania elektronicznego współużytego z dostawcą konfiguracji. Wszystkie funkcje fakturowania elektronicznego udostępniane przez firmę Microsoft są udostępniane wszystkim firmom. Automatycznie masz dostęp do wszystkich funkcji fakturowania elektronicznego, które firma Microsoft udostępnia i publikuje w globalnym repozytorium.

Aby rozpocząć pracę z funkcjami fakturowania elektronicznego współużytkowanych przez dostawcę konfiguracji, zaimportuj je do wystąpienia usługi Regulatory Configuration Service (RCS) z repozytorium globalnym. Następnie przejrzyj szczegóły funkcji, takie jak konfiguracje i potoki przetwarzania raportowania elektronicznego.

## <a name="import-a-feature-from-the-global-repository"></a>Importowanie funkcji z repozytorium globalnego

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
3. Wybierz opcję **Import**, aby otworzyć wyszukiwanie **Importuj funkcję z repozytorium globalnego**.
4. Aby przeglądać funkcje fakturowania elektronicznego w Globalnym repozytorium, które są dostępne dla określonego dostawcy konfiguracji, zsynchronizuj wystąpienie RCS organizacji, wybierając **Synchronizuj**. Po zakończeniu synchronizacji lista dostępnych funkcji fakturowania elektronicznego jest aktualizowana z repozytorium globalnego. Ta aktualizacja może potrwać kilka minut.
5. Wybierz funkcję do zaimportowania, a następnie wybierz **Importuj**.

Aby wyświetlić zaimportowaną funkcję fakturowania elektronicznego, upewnij się, że wybrano odpowiedniego dostawcę konfiguracji. Domyślnie funkcje utworzone przez aktywnego dostawcę konfiguracji są automatycznie filtrowane. Możesz dostosować filtr, aby wyświetlić funkcje utworzone przez innych dostawców, na przykład dostawcę konfiguracji firmy Microsoft.

Teraz można pracować z zaimportowaną funkcją. Zaimportowaną funkcję można przejrzeć i utworzyć nową.

> [!NOTE]
> Funkcję można zmodyfikować tylko w przypadku, gdy została utworzona przez aktualnie aktywny dostawca konfiguracji. Można utworzyć nową funkcję, używając funkcji oryginalnej jako podstawy. Następnie można dokonać wymaganych zmian lub skonfigurować parametry.

Gdy firma Microsoft lub inna firma, która udostępnia funkcje globalizacji Twojej firmie, aktualizuje funkcje, które zostały przez Ciebie zaimportowane, możesz sprawdzić dostępność zaktualizowanych wersji, wybierając **Sprawdź aktualizacje funkcji** w sekcji **Powiązane ustawienia** w **Funkcje globalizacji** obszar roboczy.

Jeśli widać aktualizacje funkcji, która jest szablonem, można zaimportować nową wersję po zsynchronizowaniu listy opublikowanych funkcji w repozytorium globalnym.
