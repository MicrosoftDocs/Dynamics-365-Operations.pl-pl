---
title: Konfiguruj pobieranie dla grupy
description: W tym temacie opisano sposób konfigurowania funkcji pobierania dla grupy oraz stosowania potwierdzania towaru z pobieraniem dla grupy.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da11a474e1bb031fac26e04c91cbdbab5f62eb0b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977360"
---
# <a name="set-up-cluster-picking"></a>Konfiguruj pobieranie dla grupy

[!include[banner](../includes/banner.md)]

W tym temacie opisano sposób umożliwienia pracownikom korzystania z urządzeń przenośnych do pobierania grupowania pracy pobrania, w celu umożliwienia pobrania towarów z jednej lokalizacji dla wielu zleceń pracy w tym samym czasie. Nazywa się to *pobieraniem dla grup*.

## <a name="about-cluster-picking"></a>Pobieranie dla grupy — informacje

Po zwolnieniu zleceń pracy do magazynu, pracownik może użyć urządzenia przenośnego do przypisywania zamówień do grupy. Grupa organizuje pracę pobrania dla pracownika. Po przypisaniu zlecenia pracy do grupy, pracownik należy użyć pobierania dla grupy do wykonania pracy pobrania dla zamówienia. Pracownik nie może stosować innych metod pobierania. Jeśli zlecenie pracy jest przypisane do grupy przez pomyłkę, pracownik musi podzielić grupę i następnie utworzyć ją ponownie.

W razie potrzeby, pracownik może przekazać grupę innemu pracownikowi. Powoduje to zmianę stanu grupy na Zdany. Jeżeli pracownik używa urządzenia przenośnego do wskazania, że praca pobierania i odkładania została zakończona, wysyłka lub załadunek muszą zostać potwierdzone na kliencie.

## <a name="enable-cluster-picking"></a>Włączanie pobierania dla grupy

Aby włączyć pobieranie dla grupy, należy skonfigurować następujące opcje:

- **Profile grup** — umożliwia określenie, czy automatycznie generować identyfikatory grupy, liczbę pozycji do użycia, kiedy likwidować grupy i jak ustawiać sekwencje i przeprowadzać sprawdzanie dla pracy pobierania.

- **Szablony pracy** — umożliwia definiowanie sposobu tworzenia pracy pobierania dla pobierania dla grup.

- **Dyrektywy lokalizacji** — umożliwia określenie miejsca pobierania towarów i miejsca ich odkładania.

- **Elementy menu urządzenia przenośnego** — Umożliwia skonfigurowanie menu urządzenia przenośnego do wykorzystania istniejącej pracy, która jest sterowana przez pobieranie dla grup. Następnie należy dodać element menu do menu urządzenia przenośnego, tak aby był wyświetlany na urządzeniach przenośnych.

- **Parametry zarządzania magazynem** — służy do określenia numeracji, która ma być używana, jeśli chcesz wygenerować identyfikatory grup.

## <a name="set-up-a-cluster-profile"></a>Konfigurowanie profilu grupy

Aby skonfigurować profil grupy, należy wykonać następujące czynności:

1. Kliknij kolejno pozycje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Profile grup**.

1. Kliknij przycisk **Nowy**, aby utworzyć nowy profil.

1. Kliknij przycisk **Tworzenie grupy**, a następnie w obszarze **Sortowanie grup** kliknij przycisk **Nowy**, aby skonfigurować kryteria sortowania grupy. Kryteria sortowania kontrolują kolejność, w której pracownik będzie wykonywał pracę pobierania. Można dodać dowolną liczbę kryteriów.

1. W polu **Numer sekwencyjny** wprowadź liczbę określającą kolejność, w jakiej mają być przetwarzane kryteria sortowania.

1. W polu **Nazwa pola**, wybierz pole, które będzie określać sortowanie. Na przykład, jeśli wybierzesz pole **WMSLocationId**, praca zostanie posortowana według lokalizacji.

1. W polu **Sortowanie** wybierz jedną z poniższych opcji.

| **Opcja**     | **Opis**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Rosnąco**  | Praca pobierania jest uporządkowana w kolejności rosnącej, na podstawie kryteriów sortowania. Na przykład, jeśli używasz pola **WMSLocationId** jako kryterium sortowania, a dana nazwa lokalizacji to 1, 2, 3 i 4, najpierw wybrana zostanie lokalizacja 4. |
| **Malejąco** | Praca pobierania jest uporządkowana w kolejności malejącej, na podstawie kryteriów sortowania. Na przykład, jeśli używasz pola **WMSLocationId** jako kryterium sortowania, a dana nazwa lokalizacji to 1, 2, 3 i 4, najpierw wybrana zostanie lokalizacja 1. |

## <a name="item-confirmation"></a>Potwierdzanie towarów

W przypadku stosowania pobierania dla grupy bardzo ważne jest potwierdzanie towarów dodawanych do grup. Weryfikowanie może się odbywać w trakcie procesu pobierania dla grup. Konfiguracja zależy od ustawień kodów kreskowych produktów.

### <a name="set-up-item-verification-with-cluster-picking"></a>Konfigurowanie weryfikowania towarów w trakcie pobierania dla grupy

1. Na urządzeniu przenośnym w menu otwórz formularz ustawień potwierdzenia pracy: **Zarządzanie magazynem** \> **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.

1. Na urządzeniu przenośnym w menu otwórz pozycję **Konfiguracja potwierdzenia pracy**. Opcja **Potwierdzenie produktu** umożliwia weryfikowanie każdego artykułu w zapasach z urządzenia przenośnego podczas skanowania.
