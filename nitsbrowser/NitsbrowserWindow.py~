# -*- Mode: Python; coding: utf-8; indent-tabs-mode: nil; tab-width: 4 -*-
### BEGIN LICENSE
# This file is in the public domain
### END LICENSE

from locale import gettext as _

from gi.repository import Gtk,WebKit # pylint: disable=E0611
import logging
logger = logging.getLogger('nitsbrowser')

from nitsbrowser_lib import Window
from nitsbrowser.AboutNitsbrowserDialog import AboutNitsbrowserDialog
from nitsbrowser.PreferencesNitsbrowserDialog import PreferencesNitsbrowserDialog

# See nitsbrowser_lib.Window.py for more details about how this class works
class NitsbrowserWindow(Window):
    __gtype_name__ = "NitsbrowserWindow"
    
    def finish_initializing(self, builder): # pylint: disable=E1002
        """Set up the main window"""
        super(NitsbrowserWindow, self).finish_initializing(builder)

        self.AboutDialog = AboutNitsbrowserDialog
        self.PreferencesDialog = PreferencesNitsbrowserDialog

        # Code for other initialization actions should be added here. (NOte for self: plan is to start with refresh button and then the body) 
 
        self.refreshbutton = self.builder.get_object("refreshbutton")
        self.urlentry = self.builder.get_object("urlentry")
        self.scrolledwindow = self.builder.get_object("scrolledwindow")
        self.toolbar = self.builder.get_object("toolbar")

        context = self.toolbar.get_style_context()
        context.add_class(Gtk.STYLE_CLASS_PRIMARY_TOOLBAR)

        self.webview= WebKit.WebView()

        self.scrolledwindow.add(self.webview)
        self.webview.show()

    def on_refreshbutton_clicked(self,widget):
            self.webview.reload()

    def on_urlentry_activate(self, widget):
            url = widget.get_text()

            self.webview.open(url)




















