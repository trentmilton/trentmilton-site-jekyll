---
layout: post
title: UISearchController Error
categories: []
tags: [uisearchcontroller, swift]
published: true

---

A pesky bug has been appearing out of nowhere while dabbling with swift.

> Attempting to load the view of a view controller while it is deallocating is not allowed and may result in undefined behavior (<UISearchController: 0x79a39050>)

### Solution

The short of it involved changing:

	var searchController = UISearchController()

to:

	var searchController: UISearchController!
