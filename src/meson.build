linker_soversion = '1.0.0'

subdir('linker')
subdir('glib')
subdir('gobject')
subdir('gthread')
subdir('graphene')
subdir('cairo')
subdir('harfbuzz')
subdir('pango')
subdir('gio')
subdir('gdkpixbuf')
subdir('atk')
subdir('gdk')
subdir('rsvg')
subdir('gsk')
subdir('gtk')
subdir('adw')
subdir('sourceview')
subdir('soup')
subdir('shumate')


################################## LINKER-D #########################################

linker_files = files('linker/Exception.d', 'linker/loader.d', 'linker/Loader.d', 'linker/exception.d')

linker = library('linker_d',
    sources: linker_files,
    install: true,
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_linker = import('pkgconfig')
pkg_linker.generate(name: 'linker',
              libraries: linker,
              version: meson.project_version(),
              description: 'Links the gtk library`s.',
              d_module_versions: ['1.0.0', 1]
)

################################## GOBJECT-D (Glib) #########################################

gobject_files = files('gobject/Closure.d', 'gobject/Signals.d', 'gobject/ValueArray.d', 'gobject/CClosure.d', 'gobject/SignalGroup.d', 'gobject/Boxed.d', 'gobject/BindingGroup.d', 'gobject/ParamSpec.d', 'gobject/TypeModule.d', 'gobject/Type.d', 'gobject/DClosure.d', 'gobject/TypeValueTable.d', 'gobject/TypeClass.d', 'gobject/TypePluginIF.d', 'gobject/Value.d', 'gobject/ObjectClass.d', 'gobject/WeakRef.d', 'gobject/Binding.d', 'gobject/Enums.d', 'gobject/Flags.d', 'gobject/ObjectG.d', 'gobject/TypeInterface.d', 'gobject/ParamSpecPool.d', 'gobject/TypeInstance.d', 'gobject/TypePluginT.d', 'gobject/c/types.d', 'gobject/c/functions.d')

gobject = library('gobject_d',
    sources: gobject_files,
    install: true,
    version: meson.project_version(),
    soversion: linker_soversion,
)

################################## GTHREAD-D (Glib)#########################################

gthread_files = files('gthread/Private.d', 'gthread/RecMutex.d', 'gthread/Cond.d', 'gthread/RWLock.d', 'gthread/Thread.d', 'gthread/Mutex.d', 'gthread/Once.d', 'gthread/c/types.d', 'gthread/c/functions.d')

gthread = library('gthread_d',
    sources: gthread_files,
    install: true,
    version: meson.project_version(),
    soversion: linker_soversion,
)

###################################### GLIB-D ##############################################

glib_files = files('glib/Private.d', 'glib/MatchInfo.d', 'glib/RecMutex.d', 'glib/FileUtils.d', 'glib/TimeZone.d', 'glib/TestLogBuffer.d', 'glib/Checksum.d', 'glib/VariantType.d', 'glib/Cond.d', 'glib/KeyFile.d', 'glib/GException.d', 'glib/UnixUtils.d', 'glib/SequenceIter.d', 'glib/StringG.d', 'glib/IConv.d', 'glib/VariantDict.d', 'glib/Spawn.d', 'glib/DateTime.d', 'glib/Hmac.d', 'glib/HashTable.d', 'glib/ShellUtils.d', 'glib/Sequence.d', 'glib/ThreadPool.d', 'glib/CharacterSet.d', 'glib/Pattern.d', 'glib/TimeVal.d', 'glib/BBTree.d', 'glib/URI.d', 'glib/Str.d', 'glib/MemorySlice.d', 'glib/ByteArray.d', 'glib/Hostname.d', 'glib/Unicode.d', 'glib/ScannerG.d', 'glib/DataSet.d', 'glib/Bytes.d', 'glib/RandG.d', 'glib/MappedFile.d', 'glib/Version.d', 'glib/OptionGroup.d', 'glib/MainLoop.d', 'glib/TestLogMsg.d', 'glib/Variant.d', 'glib/BookmarkFile.d', 'glib/Date.d', 'glib/UriParamsIter.d', 'glib/TrashStack.d', 'glib/MainContext.d', 'glib/AsyncQueue.d', 'glib/Hook.d', 'glib/Node.d', 'glib/ConstructionException.d', 'glib/TestCase.d', 'glib/DataList.d', 'glib/Internationalization.d', 'glib/ErrorG.d', 'glib/Timeout.d', 'glib/Timer.d', 'glib/Uuid.d', 'glib/ArrayG.d', 'glib/HashTableIter.d', 'glib/ListSG.d', 'glib/Idle.d', 'glib/StrvBuilder.d', 'glib/VariantIter.d', 'glib/GLib.d', 'glib/HookList.d', 'glib/Util.d', 'glib/IOChannel.d', 'glib/MessageLog.d', 'glib/Atomic.d', 'glib/Module.d', 'glib/RWLock.d', 'glib/PtrArray.d', 'glib/Regex.d', 'glib/ListG.d', 'glib/Directory.d', 'glib/Memory.d', 'glib/Thread.d', 'glib/StringChunk.d', 'glib/VariantBuilder.d', 'glib/Quark.d', 'glib/Mutex.d', 'glib/TreeNode.d', 'glib/TestSuite.d', 'glib/Source.d', 'glib/Once.d', 'glib/SimpleXML.d', 'glib/QueueG.d', 'glib/Base64.d', 'glib/Child.d', 'glib/Messages.d', 'glib/OptionContext.d', 'glib/c/types.d', 'glib/c/functions.d')

glib = library('glib_d',
    sources: glib_files,
    install: true,
    link_with: [gobject, gthread, linker],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_glib = import('pkgconfig')
pkg_glib.generate(name: 'glib_d',
              libraries: [glib, gobject, gthread, linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

##################################### Graphene ##############################################

grap_files = files(['graphene/Frustum.d', 'graphene/Plane.d', 'graphene/Vec2.d', 'graphene/Ray.d', 'graphene/Euler.d', 'graphene/Point.d', 'graphene/Quaternion.d', 'graphene/Vec4.d', 'graphene/Point3D.d', 'graphene/Size.d', 'graphene/Matrix.d', 'graphene/Rect.d', 'graphene/Sphere.d', 'graphene/Triangle.d', 'graphene/Quad.d', 'graphene/Vec3.d', 'graphene/Box.d', 'graphene/c/types.d', 'graphene/c/functions.d'])

grap = library('graphene_d',
    sources: grap_files,
    install: true,
    link_with: [glib, linker],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_grap = import('pkgconfig')
pkg_grap.generate(name: 'graphene_d',
              libraries: [grap, glib,linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

##################################### Cairo ##############################################

cairo_files = files(['cairo/FontOption.d', 'cairo/ScriptSurface.d', 'cairo/Pattern.d', 'cairo/RasterSource.d', 'cairo/Version.d', 'cairo/Types.d', 'cairo/Surface.d', 'cairo/RecordingSurface.d', 'cairo/Script.d', 'cairo/MeshPattern.d', 'cairo/ImageSurface.d', 'cairo/Region.d', 'cairo/PostScriptSurface.d', 'cairo/PdfSurface.d', 'cairo/Device.d', 'cairo/Matrix.d', 'cairo/Context.d', 'cairo/ScaledFont.d', 'cairo/Status.d', 'cairo/UserFontFace.d', 'cairo/FontFace.d', 'cairo/SvgSurface.d', 'cairo/c/types.d', 'cairo/c/functions.d'])

cairo = library('cairo_d',
    sources: cairo_files,
    install: true,
    link_with: [glib, linker],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_cairo = import('pkgconfig')
pkg_cairo.generate(name: 'cairo_d',
              libraries: [cairo, glib,linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)


################################### harfbuzz ##############################################

harfbuzz_files = files(['harfbuzz/segment_properties_t.d', 'harfbuzz/user_data_key_t.d', 'harfbuzz/unicode_funcs_t.d', 'harfbuzz/buffer_t.d', 'harfbuzz/map_t.d', 'harfbuzz/glyph_info_t.d', 'harfbuzz/ot_math_glyph_variant_t.d', 'harfbuzz/feature_t.d', 'harfbuzz/glyph_position_t.d', 'harfbuzz/blob_t.d', 'harfbuzz/shape_plan_t.d', 'harfbuzz/variation_t.d', 'harfbuzz/draw_funcs_t.d', 'harfbuzz/ot_math_glyph_part_t.d', 'harfbuzz/language_t.d', 'harfbuzz/set_t.d', 'harfbuzz/font_t.d', 'harfbuzz/face_t.d', 'harfbuzz/font_funcs_t.d', 'harfbuzz/c/types.d', 'harfbuzz/c/functions.d', 'harfbuzz/c/types.d', 'harfbuzz/c/functions.d'])

harfbuzz = library('harfbuzz_d',
    sources: harfbuzz_files,
    install: true,
    link_with: [glib, linker],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_harfbuzz = import('pkgconfig')
pkg_harfbuzz.generate(name: 'harfbuzz_d',
              libraries: [harfbuzz, glib,linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### pango ##############################################

pango_files = files(['pango/PgAttributeSize.d', 'pango/PgLayoutLine.d', 'pango/PgColor.d', 'pango/PgVertical.d', 'pango/PgAttributeLanguage.d', 'pango/PgCairoFontMap.d', 'pango/PgFontFace.d', 'pango/PgItem.d', 'pango/PgFontFamily.d', 'pango/PgFontDescription.d', 'pango/PgAttributeList.d', 'pango/PgContext.d', 'pango/PgFontMetrics.d', 'pango/PgScriptIter.d', 'pango/PgAttributeIterator.d', 'pango/PgLayoutIter.d', 'pango/PgGlyphItemIter.d', 'pango/PgAttributeShape.d', 'pango/PgFontsetSimple.d', 'pango/PgCoverage.d', 'pango/PgScript.d', 'pango/PgFont.d', 'pango/PgLanguage.d', 'pango/PgFontset.d', 'pango/PgGlyphItem.d', 'pango/PgVersion.d', 'pango/PgRenderer.d', 'pango/PgCairo.d', 'pango/PgMiscellaneous.d', 'pango/PgAttributeFontDesc.d', 'pango/PgFontMap.d', 'pango/PgLayout.d', 'pango/PgTabArray.d', 'pango/PgAttribute.d', 'pango/PgGlyphString.d', 'pango/PgMatrix.d', 'pango/c/types.d', 'pango/c/functions.d', 'pango/c/types.d', 'pango/c/functions.d'])


pango = library('pango_d',
    sources: pango_files,
    install: true,
    link_with: [glib,linker, harfbuzz, cairo],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_pango = import('pkgconfig')
pkg_pango.generate(name: 'pango_d',
              libraries: [pango, glib,linker, harfbuzz, cairo],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### GIO ##############################################

gio_files = files(['pango/PgAttributeSize.d', 'pango/PgLayoutLine.d', 'pango/PgColor.d', 'pango/PgVertical.d', 'pango/PgAttributeLanguage.d', 'pango/PgCairoFontMap.d', 'pango/PgFontFace.d', 'pango/PgItem.d', 'pango/PgFontFamily.d', 'pango/PgFontDescription.d', 'pango/PgAttributeList.d', 'pango/PgContext.d', 'pango/PgFontMetrics.d', 'pango/PgScriptIter.d', 'pango/PgAttributeIterator.d', 'pango/PgLayoutIter.d', 'pango/PgGlyphItemIter.d', 'pango/PgAttributeShape.d', 'pango/PgFontsetSimple.d', 'pango/PgCoverage.d', 'pango/PgScript.d', 'pango/PgFont.d', 'pango/PgLanguage.d', 'pango/PgFontset.d', 'pango/PgGlyphItem.d', 'pango/PgVersion.d', 'pango/PgRenderer.d', 'pango/PgCairo.d', 'pango/PgMiscellaneous.d', 'pango/PgAttributeFontDesc.d', 'pango/PgFontMap.d', 'pango/PgLayout.d', 'pango/PgTabArray.d', 'pango/PgAttribute.d', 'pango/PgGlyphString.d', 'pango/PgMatrix.d', 'pango/c/types.d', 'pango/c/functions.d', 'pango/c/types.d', 'pango/c/functions.d'])


gio = library('gio_d',
    sources: gio_files,
    install: true,
    link_with: [glib, linker],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_gio = import('pkgconfig')
pkg_gio.generate(name: 'gio_d',
              libraries: [gio, glib,linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### gdkpixbuf ##############################################

gdkpixbuf_files = files(['gdkpixbuf/Pixdata.d', 'gdkpixbuf/PixbufAnimationIter.d', 'gdkpixbuf/PixbufFormat.d', 'gdkpixbuf/PixbufLoader.d', 'gdkpixbuf/PixbufAnimation.d', 'gdkpixbuf/PixbufNonAnim.d', 'gdkpixbuf/PixbufSimpleAnimation.d', 'gdkpixbuf/Pixbuf.d', 'gdkpixbuf/c/types.d', 'gdkpixbuf/c/functions.d', 'gdkpixbuf/c/types.d', 'gdkpixbuf/c/functions.d'])


gdkpixbuf = library('gdkpixbuf_d',
    sources: gdkpixbuf_files,
    install: true,
    link_with: [glib, linker, gio],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_gdkpixbuf = import('pkgconfig')
pkg_gdkpixbuf.generate(name: 'gdkpixbuf_d',
              libraries: [gdkpixbuf, gio, glib,linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### atk ##############################################

atk_files = files(['atk/StateSet.d', 'atk/ObjectFactory.d', 'atk/Registry.d', 'atk/TableIF.d', 'atk/WindowIF.d', 'atk/NoOpObject.d', 'atk/ComponentIF.d', 'atk/ImplementorT.d', 'atk/ValueT.d', 'atk/TextT.d', 'atk/ActionIF.d', 'atk/SelectionIF.d', 'atk/StreamableContentT.d', 'atk/ComponentT.d', 'atk/ActionT.d', 'atk/State.d', 'atk/EditableTextIF.d', 'atk/TableCellIF.d', 'atk/Version.d', 'atk/TextIF.d', 'atk/SelectionT.d', 'atk/Hyperlink.d', 'atk/GObjectAccessible.d', 'atk/ValueIF.d', 'atk/TableT.d', 'atk/TableCellT.d', 'atk/TextRange.d', 'atk/Socket.d', 'atk/HypertextIF.d', 'atk/HyperlinkImplIF.d', 'atk/ImageT.d', 'atk/ImplementorIF.d', 'atk/Range.d', 'atk/ObjectAtk.d', 'atk/EditableTextT.d', 'atk/HyperlinkImplT.d', 'atk/StreamableContentIF.d', 'atk/WindowT.d', 'atk/Util.d', 'atk/Misc.d', 'atk/HypertextT.d', 'atk/Relation.d', 'atk/Rectangle.d', 'atk/NoOpObjectFactory.d', 'atk/RelationSet.d', 'atk/Plug.d', 'atk/ImageIF.d', 'atk/DocumentIF.d', 'atk/DocumentT.d', 'atk/c/types.d', 'atk/c/functions.d', 'atk/c/types.d', 'atk/c/functions.d'])


atk = library('atk_d',
    sources: atk_files,
    install: true,
    link_with: [glib, linker],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_atk = import('pkgconfig')
pkg_atk.generate(name: 'atk_d',
              libraries: [atk, glib, linker],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### gdk ##############################################

gdk_files = files(['gdk/Cursor.d', 'gdk/DragSurfaceT.d', 'gdk/Seat.d', 'gdk/ToplevelT.d', 'gdk/GLTexture.d', 'gdk/ToplevelSize.d', 'gdk/DragSurfaceIF.d', 'gdk/PaintableIF.d', 'gdk/DevicePadIF.d', 'gdk/Display.d', 'gdk/MemoryTexture.d', 'gdk/PopupLayout.d', 'gdk/PopupT.d', 'gdk/EventSequence.d', 'gdk/Snapshot.d', 'gdk/VulkanContext.d', 'gdk/ContentFormats.d', 'gdk/FocusEvent.d', 'gdk/Drop.d', 'gdk/ProximityEvent.d', 'gdk/Surface.d', 'gdk/Event.d', 'gdk/MonitorGdk.d', 'gdk/ToplevelIF.d', 'gdk/CrossingEvent.d', 'gdk/FileList.d', 'gdk/ContentProvider.d', 'gdk/ScrollEvent.d', 'gdk/ButtonEvent.d', 'gdk/ToplevelLayout.d', 'gdk/GrabBrokenEvent.d', 'gdk/PadEvent.d', 'gdk/Clipboard.d', 'gdk/Device.d', 'gdk/GLContext.d', 'gdk/DeleteEvent.d', 'gdk/AppLaunchContext.d', 'gdk/ContentSerializer.d', 'gdk/FrameTimings.d', 'gdk/ContentDeserializer.d', 'gdk/PaintableT.d', 'gdk/TouchEvent.d', 'gdk/DisplayManager.d', 'gdk/ContentFormatsBuilder.d', 'gdk/Rectangle.d', 'gdk/Drag.d', 'gdk/KeyEvent.d', 'gdk/Keysyms.d', 'gdk/DNDEvent.d', 'gdk/DevicePadT.d', 'gdk/Texture.d', 'gdk/DeviceTool.d', 'gdk/TouchpadEvent.d', 'gdk/MotionEvent.d', 'gdk/DrawContext.d', 'gdk/CairoContext.d', 'gdk/FrameClock.d', 'gdk/RGBA.d', 'gdk/PopupIF.d', 'gdk/c/types.d', 'gdk/c/functions.d', 'gdk/c/types.d', 'gdk/c/functions.d'])


gdk = library('gdk_d',
    sources: gdkpixbuf_files,
    install: true,
    link_with: [glib, linker, gio, pango, gdkpixbuf],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_gdk = import('pkgconfig')
pkg_gdk.generate(name: 'gdk_d',
              libraries: [gdk, glib, linker, cairo, gio, pango, gdkpixbuf],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### rsvg ##############################################

rsvg_files = files(['rsvg/Handle.d','rsvg/c/types.d','rsvg/c/functions.d'])


rsvg = library('rsvg_d',
    sources: rsvg_files,
    install: true,
    link_with: [glib, linker, cairo,gdkpixbuf],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_rsvg  = import('pkgconfig')
pkg_rsvg.generate(name: 'rsvg_d',
              libraries: [rsvg, glib, linker, cairo,gdkpixbuf],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################### gsk ##############################################

gsk_files = files(['gsk/ShaderArgsBuilder.d', 'gsk/GLShaderNode.d', 'gsk/GLRenderer.d', 'gsk/ContainerNode.d', 'gsk/OpacityNode.d', 'gsk/Transform.d', 'gsk/NglRenderer.d', 'gsk/BlurNode.d', 'gsk/ClipNode.d', 'gsk/RepeatingLinearGradientNode.d', 'gsk/RadialGradientNode.d', 'gsk/ColorMatrixNode.d', 'gsk/CairoNode.d', 'gsk/ConicGradientNode.d', 'gsk/TextNode.d', 'gsk/ColorNode.d', 'gsk/TransformNode.d', 'gsk/RepeatNode.d', 'gsk/RepeatingRadialGradientNode.d', 'gsk/DebugNode.d', 'gsk/CairoRenderer.d', 'gsk/BroadwayRenderer.d', 'gsk/RoundedRect.d', 'gsk/BlendNode.d', 'gsk/Renderer.d', 'gsk/InsetShadowNode.d', 'gsk/LinearGradientNode.d', 'gsk/ShadowNode.d', 'gsk/TextureNode.d', 'gsk/CrossFadeNode.d', 'gsk/RoundedClipNode.d', 'gsk/GLShader.d', 'gsk/BorderNode.d', 'gsk/RenderNode.d', 'gsk/OutsetShadowNode.d', 'gsk/c/types.d', 'gsk/c/functions.d', 'gsk/c/types.d', 'gsk/c/functions.d'])


gsk = library('gsk_d',
    sources: gsk_files,
    install: true,
    link_with: [gdk, glib, linker, cairo, grap],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_gsk  = import('pkgconfig')
pkg_gsk.generate(name: 'rsvg_d',
              libraries: [gsk, gdkpixbuf, glib, linker, cairo, grap],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)


################################### gtk ##############################################

gtk_files = files(['gtk/WindowControls.d', 'gtk/AnyFilter.d', 'gtk/CellRendererProgress.d', 'gtk/PropertyExpression.d', 'gtk/MediaStream.d', 'gtk/TreeDragSourceT.d', 'gtk/GridView.d', 'gtk/NativeDialog.d', 'gtk/TextTag.d', 'gtk/PrintContext.d', 'gtk/PageSetup.d', 'gtk/GesturePan.d', 'gtk/MnemonicTrigger.d', 'gtk/BuilderScopeT.d', 'gtk/HeaderBar.d', 'gtk/WidgetPaintable.d', 'gtk/RecentInfo.d', 'gtk/TreeListModel.d', 'gtk/MediaControls.d', 'gtk/CellLayoutIF.d', 'gtk/TreeListRow.d', 'gtk/Button.d', 'gtk/Overlay.d', 'gtk/SignalListItemFactory.d', 'gtk/FontChooserIF.d', 'gtk/LayoutChild.d', 'gtk/MultiSorter.d', 'gtk/Application.d', 'gtk/ActionableT.d', 'gtk/ColorButton.d', 'gtk/GestureClick.d', 'gtk/LevelBar.d', 'gtk/SpinButton.d', 'gtk/EventControllerLegacy.d', 'gtk/ParamSpecExpression.d', 'gtk/SelectionModelIF.d', 'gtk/FontChooserT.d', 'gtk/SingleSelection.d', 'gtk/Window.d', 'gtk/FixedLayoutChild.d', 'gtk/FileChooserNative.d', 'gtk/SliceListModel.d', 'gtk/CellRendererPixbuf.d', 'gtk/StringSorter.d', 'gtk/EveryFilter.d', 'gtk/WindowHandle.d', 'gtk/SearchEntry.d', 'gtk/DropTargetAsync.d', 'gtk/StackPage.d', 'gtk/LinkButton.d', 'gtk/Spinner.d', 'gtk/Popover.d', 'gtk/IconPaintable.d', 'gtk/AppChooserButton.d', 'gtk/OverlayLayoutChild.d', 'gtk/ATContext.d', 'gtk/MessageDialog.d', 'gtk/ColorChooserT.d', 'gtk/FileFilter.d', 'gtk/OverlayLayout.d', 'gtk/IconView.d', 'gtk/CenterBox.d', 'gtk/Fixed.d', 'gtk/TreeExpander.d', 'gtk/Sorter.d', 'gtk/Scrollbar.d', 'gtk/CellView.d', 'gtk/TextView.d', 'gtk/EventControllerKey.d', 'gtk/Stack.d', 'gtk/DirectoryList.d', 'gtk/TreeSortableIF.d', 'gtk/CellAreaBox.d', 'gtk/FileChooserWidget.d', 'gtk/ActionBar.d', 'gtk/GestureLongPress.d', 'gtk/EditableLabel.d', 'gtk/Bitset.d', 'gtk/Filter.d', 'gtk/PasswordEntry.d', 'gtk/ScrolledWindow.d', 'gtk/BitsetIter.d', 'gtk/BoxLayout.d', 'gtk/EditableT.d', 'gtk/CellAreaClass.d', 'gtk/ShortcutAction.d', 'gtk/ComboBox.d', 'gtk/AboutDialog.d', 'gtk/Statusbar.d', 'gtk/TreeViewColumn.d', 'gtk/NativeIF.d', 'gtk/Snapshot.d', 'gtk/TreeStore.d', 'gtk/DragSource.d', 'gtk/PaperSize.d', 'gtk/StyleContext.d', 'gtk/PasswordEntryBuffer.d', 'gtk/Border.d', 'gtk/OrientableIF.d', 'gtk/BuildableIF.d', 'gtk/CellRendererSpin.d', 'gtk/WindowGroup.d', 'gtk/Picture.d', 'gtk/CssProvider.d', 'gtk/RootIF.d', 'gtk/TreeListRowSorter.d', 'gtk/PrintSettings.d', 'gtk/Widget.d', 'gtk/CssSection.d', 'gtk/EditableIF.d', 'gtk/TreeRowReference.d', 'gtk/ClosureExpression.d', 'gtk/Expression.d', 'gtk/SelectionFilterModel.d', 'gtk/NoSelection.d', 'gtk/ColorChooserIF.d', 'gtk/EntryCompletion.d', 'gtk/EventControllerScroll.d', 'gtk/TreeModelFilter.d', 'gtk/SortListModel.d', 'gtk/CClosureExpression.d', 'gtk/Implement.d', 'gtk/Shortcut.d', 'gtk/CellArea.d', 'gtk/EntryBuffer.d', 'gtk/KeyvalTrigger.d', 'gtk/GestureDrag.d', 'gtk/Text.d', 'gtk/MultiSelection.d', 'gtk/ShortcutsShortcut.d', 'gtk/ScrollableIF.d', 'gtk/CenterLayout.d', 'gtk/NotebookPage.d', 'gtk/CellRendererText.d', 'gtk/ListItem.d', 'gtk/MultiFilter.d', 'gtk/GridLayout.d', 'gtk/InfoBar.d', 'gtk/TreeDragDestT.d', 'gtk/FlowBoxChild.d', 'gtk/ScrollableT.d', 'gtk/Requisition.d', 'gtk/Dialog.d', 'gtk/ColorChooserDialog.d', 'gtk/GestureStylus.d', 'gtk/ShortcutsSection.d', 'gtk/IMContext.d', 'gtk/CellEditableIF.d', 'gtk/StyleProviderT.d', 'gtk/DropControllerMotion.d', 'gtk/PadController.d', 'gtk/ShortcutLabel.d', 'gtk/FileChooserDialog.d', 'gtk/Viewport.d', 'gtk/StringObject.d', 'gtk/Label.d', 'gtk/DragIcon.d', 'gtk/CellAreaContext.d', 'gtk/GridLayoutChild.d', 'gtk/ShortcutsWindow.d', 'gtk/NativeT.d', 'gtk/PrintUnixDialog.d', 'gtk/CellRendererSpinner.d', 'gtk/Printer.d', 'gtk/Grid.d', 'gtk/FilterListModel.d', 'gtk/MapListModel.d', 'gtk/FileChooserT.d', 'gtk/ListStore.d', 'gtk/PageSetupUnixDialog.d', 'gtk/ColumnViewColumn.d', 'gtk/CustomSorter.d', 'gtk/BuilderCScope.d', 'gtk/PopoverMenuBar.d', 'gtk/FlattenListModel.d', 'gtk/MountOperation.d', 'gtk/ListBoxRow.d', 'gtk/LockButton.d', 'gtk/CellRendererCombo.d', 'gtk/CellRendererAccel.d', 'gtk/IconTheme.d', 'gtk/DropDown.d', 'gtk/GLArea.d', 'gtk/RecentManager.d', 'gtk/CellRenderer.d', 'gtk/EventControllerFocus.d', 'gtk/TreeView.d', 'gtk/TreeIter.d', 'gtk/GestureZoom.d', 'gtk/EventController.d', 'gtk/ActionableIF.d', 'gtk/ShortcutsGroup.d', 'gtk/TextMark.d', 'gtk/WidgetClass.d', 'gtk/CheckButton.d', 'gtk/LayoutManager.d', 'gtk/TextChildAnchor.d', 'gtk/Range.d', 'gtk/DropTarget.d', 'gtk/CellRendererToggle.d', 'gtk/TreePath.d', 'gtk/Settings.d', 'gtk/AppChooserIF.d', 'gtk/Notebook.d', 'gtk/TextTagTable.d', 'gtk/SizeGroup.d', 'gtk/BuilderListItemFactory.d', 'gtk/SelectionModelT.d', 'gtk/BuilderScopeIF.d', 'gtk/BuildableParseContext.d', 'gtk/ListItemFactory.d', 'gtk/ExpressionWatch.d', 'gtk/MediaFile.d', 'gtk/Tooltip.d', 'gtk/DrawingArea.d', 'gtk/CustomLayout.d', 'gtk/ColumnView.d', 'gtk/BoolFilter.d', 'gtk/IMContextSimple.d', 'gtk/PopoverMenu.d', 'gtk/BinLayout.d', 'gtk/FontChooserWidget.d', 'gtk/ConstraintLayoutChild.d', 'gtk/ShortcutManagerT.d', 'gtk/CellLayoutT.d', 'gtk/Builder.d', 'gtk/TreeModelIF.d', 'gtk/TreeSelection.d', 'gtk/Switch.d', 'gtk/Frame.d', 'gtk/BuildableT.d', 'gtk/ProgressBar.d', 'gtk/SymbolicPaintableT.d', 'gtk/GestureRotate.d', 'gtk/PrintJob.d', 'gtk/ConstraintTargetIF.d', 'gtk/ListBox.d', 'gtk/TreeModelSort.d', 'gtk/VolumeButton.d', 'gtk/TreeSortableT.d', 'gtk/StringList.d', 'gtk/AccessibleT.d', 'gtk/AlternativeTrigger.d', 'gtk/Paned.d', 'gtk/Constraint.d', 'gtk/TreeModelT.d', 'gtk/ToggleButton.d', 'gtk/EmojiChooser.d', 'gtk/ShortcutManagerIF.d', 'gtk/FileChooserIF.d', 'gtk/NamedAction.d', 'gtk/AccessibleIF.d', 'gtk/ConstraintTargetT.d', 'gtk/ActivateAction.d', 'gtk/StackSidebar.d', 'gtk/Video.d', 'gtk/GestureSingle.d', 'gtk/ListView.d', 'gtk/MenuButton.d', 'gtk/PrintOperation.d', 'gtk/SymbolicPaintableIF.d', 'gtk/SignalAction.d', 'gtk/GestureSwipe.d', 'gtk/StyleProviderIF.d', 'gtk/StringFilter.d', 'gtk/Scale.d', 'gtk/FontButton.d', 'gtk/MnemonicAction.d', 'gtk/ScaleButton.d', 'gtk/NumericSorter.d', 'gtk/TreeDragSourceIF.d', 'gtk/IMMulticontext.d', 'gtk/AppChooserDialog.d', 'gtk/CustomFilter.d', 'gtk/ColorChooserWidget.d', 'gtk/TextIter.d', 'gtk/PrintOperationPreviewIF.d', 'gtk/Revealer.d', 'gtk/TextBuffer.d', 'gtk/ObjectExpression.d', 'gtk/OrientableT.d', 'gtk/BookmarkList.d', 'gtk/ConstantExpression.d', 'gtk/AspectFrame.d', 'gtk/EventControllerMotion.d', 'gtk/ListBase.d', 'gtk/Image.d', 'gtk/AppChooserT.d', 'gtk/ShortcutController.d', 'gtk/AppChooserWidget.d', 'gtk/NothingAction.d', 'gtk/Expander.d', 'gtk/Box.d', 'gtk/Entry.d', 'gtk/ConstraintLayout.d', 'gtk/ShortcutTrigger.d', 'gtk/Calendar.d', 'gtk/Adjustment.d', 'gtk/ConstraintGuide.d', 'gtk/CellEditableT.d', 'gtk/FontChooserDialog.d', 'gtk/StackSwitcher.d', 'gtk/NeverTrigger.d', 'gtk/Separator.d', 'gtk/AssistantPage.d', 'gtk/ComboBoxText.d', 'gtk/SearchBar.d', 'gtk/FixedLayout.d', 'gtk/Assistant.d', 'gtk/TreeDragDestIF.d', 'gtk/ApplicationWindow.d', 'gtk/RootT.d', 'gtk/PrintOperationPreviewT.d', 'gtk/FlowBox.d', 'gtk/Gesture.d', 'gtk/CallbackAction.d', 'gtk/c/types.d', 'gtk/c/functions.d', 'gtk/c/types.d', 'gtk/c/functions.d'])

gtk = library('gtk_d',
    sources: gsk_files,
    install: true,
    link_with: [gdk, glib, linker, gsk, grap],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_gtk  = import('pkgconfig')
pkg_gtk.generate(name: 'gtk_d',
              libraries: [gtk, gdk, glib, linker, gsk, grap],
              version: meson.project_version(),
              description: 'Glib for gtk_d.',
              d_module_versions: ['2.68.1', 1]
)

################################# sourceview #################################################

sourceview_files = files(['sourceview/CompletionProviderIF.d', 'sourceview/SpaceDrawer.d', 'sourceview/Gutter.d', 'sourceview/File.d', 'sourceview/Style.d', 'sourceview/GutterLines.d', 'sourceview/StyleSchemeChooserIF.d', 'sourceview/FileSaver.d', 'sourceview/PrintCompositor.d', 'sourceview/RegionIter.d', 'sourceview/SnippetManager.d', 'sourceview/CompletionProposalT.d', 'sourceview/Language.d', 'sourceview/CompletionContext.d', 'sourceview/View.d', 'sourceview/HoverContext.d', 'sourceview/MarkAttributes.d', 'sourceview/StyleSchemeChooserWidget.d', 'sourceview/Map.d', 'sourceview/Hover.d', 'sourceview/StyleSchemeChooserButton.d', 'sourceview/CompletionProviderT.d', 'sourceview/CompletionCell.d', 'sourceview/IndenterIF.d', 'sourceview/StyleSchemeManager.d', 'sourceview/SnippetChunk.d', 'sourceview/SearchContext.d', 'sourceview/HoverProviderIF.d', 'sourceview/LanguageManager.d', 'sourceview/Handle.d', 'sourceview/GutterRenderer.d', 'sourceview/CompletionProposalIF.d', 'sourceview/StyleScheme.d', 'sourceview/Region.d', 'sourceview/Mark.d', 'sourceview/GutterRendererPixbuf.d', 'sourceview/Tag.d', 'sourceview/SnippetContext.d', 'sourceview/CompletionWords.d', 'sourceview/CompletionSnippets.d', 'sourceview/Completion.d', 'sourceview/StyleSchemePreview.d', 'sourceview/SearchSettings.d', 'sourceview/HoverProviderT.d', 'sourceview/StyleSchemeChooserT.d', 'sourceview/VimIMContext.d', 'sourceview/Snippet.d', 'sourceview/Buffer.d', 'sourceview/FileLoader.d', 'sourceview/IndenterT.d', 'sourceview/HoverDisplay.d', 'sourceview/GutterRendererText.d', 'sourceview/Encoding.d', 'sourceview/c/types.d', 'sourceview/c/functions.d', 'sourceview/c/types.d', 'sourceview/c/functions.d'])

sourceview = library('sourview_d',
    sources: sourceview_files,
    install: true,
    link_with: [gtk, linker, glib],
    version: meson.project_version(),
    soversion: linker_soversion,
)


pkg_sourceview = import('pkgconfig')
pkg_sourceview.generate(name: 'sourview_d',
               libraries: [sourceview, glib, gtk, linker],
               version: meson.project_version(),
               description: 'Glib for gtk_d.',
               d_module_versions: ['2.68.1', 1]
)

####################################### ADW #################################################

adw_files = files(['adw/SwipeableIF.d', 'adw/PreferencesPage.d', 'adw/HeaderBar.d', 'adw/AnimationTarget.d', 'adw/TabView.d', 'adw/Application.d', 'adw/CarouselIndicatorDots.d', 'adw/Window.d', 'adw/ViewSwitcher.d', 'adw/EnumListModel.d', 'adw/ViewSwitcherBar.d', 'adw/WindowTitle.d', 'adw/CallbackAnimationTarget.d', 'adw/Carousel.d', 'adw/TabBar.d', 'adw/SplitButton.d', 'adw/PreferencesGroup.d', 'adw/LeafletPage.d', 'adw/ViewStackPage.d', 'adw/TabPage.d', 'adw/StatusPage.d', 'adw/ClampScrollable.d', 'adw/StyleManager.d', 'adw/SwipeableT.d', 'adw/ExpanderRow.d', 'adw/SpringAnimation.d', 'adw/Toast.d', 'adw/ComboRow.d', 'adw/Animation.d', 'adw/ViewSwitcherTitle.d', 'adw/ActionRow.d', 'adw/Squeezer.d', 'adw/PreferencesRow.d', 'adw/Flap.d', 'adw/Clamp.d', 'adw/SpringParams.d', 'adw/ButtonContent.d', 'adw/ToastOverlay.d', 'adw/SwipeTracker.d', 'adw/Leaflet.d', 'adw/PreferencesWindow.d', 'adw/Avatar.d', 'adw/ClampLayout.d', 'adw/ViewStack.d', 'adw/SqueezerPage.d', 'adw/CarouselIndicatorLines.d', 'adw/TimedAnimation.d', 'adw/EnumListItem.d', 'adw/Bin.d', 'adw/ApplicationWindow.d', 'adw/c/types.d', 'adw/c/functions.d', 'adw/c/types.d', 'adw/c/functions.d'])

adw = library('adw_d',
    sources: adw_files,
    install: true,
    link_with: [gtk, linker, glib],
    version: meson.project_version(),
    soversion: linker_soversion,
)


pkg_glib = import('pkgconfig')
pkg_glib.generate(name: 'adw_d',
               libraries: [adw, glib, gtk, linker],
               version: meson.project_version(),
               description: 'Glib for gtk_d.',
               d_module_versions: ['2.68.1', 1]
)


################################# soup #################################################

soup_files = files(['soup/AuthDomainBasic.d', 'soup/XMLRPCParams.d', 'soup/HSTSEnforcer.d', 'soup/RequestFile.d', 'soup/RequestHTTP.d', 'soup/SessionAsync.d', 'soup/WebsocketConnection.d', 'soup/AuthDigest.d', 'soup/Address.d', 'soup/SessionFeatureT.d', 'soup/Session.d', 'soup/AuthBasic.d', 'soup/URI.d', 'soup/Auth.d', 'soup/HSTSPolicy.d', 'soup/Cookie.d', 'soup/Logger.d', 'soup/ProxyResolverDefault.d', 'soup/PasswordManagerT.d', 'soup/PasswordManagerIF.d', 'soup/CookieJarDB.d', 'soup/AuthNegotiate.d', 'soup/AuthManager.d', 'soup/Requester.d', 'soup/ContentSniffer.d', 'soup/Date.d', 'soup/Multipart.d', 'soup/ClientContext.d', 'soup/CookieJar.d', 'soup/WebsocketExtensionDeflate.d', 'soup/MessageBody.d', 'soup/Message.d', 'soup/AuthDomainDigest.d', 'soup/MessageHeaders.d', 'soup/Cache.d', 'soup/ContentDecoder.d', 'soup/SessionFeatureIF.d', 'soup/ProxyURIResolverT.d', 'soup/ProxyResolverIF.d', 'soup/CookieJarText.d', 'soup/Request.d', 'soup/RequestData.d', 'soup/Server.d', 'soup/ProxyResolverT.d', 'soup/AuthDomain.d', 'soup/SSocket.d', 'soup/AuthNTLM.d', 'soup/WebsocketExtension.d', 'soup/Buffer.d', 'soup/ProxyURIResolverIF.d', 'soup/MultipartInputStream.d', 'soup/WebsocketExtensionManager.d', 'soup/HSTSEnforcerDB.d', 'soup/SessionSync.d', 'soup/MessageHeadersIter.d', 'soup/c/types.d', 'soup/c/functions.d', 'soup/c/types.d', 'soup/c/functions.d'])

soup = library('soup_d',
    sources: soup_files,
    install: true,
    link_with: [gio, linker, glib],
    version: meson.project_version(),
    soversion: linker_soversion,
)

pkg_soup = import('pkgconfig')
pkg_soup.generate(name: 'soup_d',
               libraries: [soup, glib, gio, linker],
               version: meson.project_version(),
               description: 'Glib for gtk_d.',
               d_module_versions: ['2.68.1', 1]
)

################################### shumate #################################################

shumate_files = files(['shumate/MapLayer.d', 'shumate/FileCache.d', 'shumate/Coordinate.d', 'shumate/Map.d', 'shumate/Layer.d', 'shumate/Point.d', 'shumate/VectorRenderer.d', 'shumate/LocationT.d', 'shumate/Marker.d', 'shumate/LicenseSh.d', 'shumate/Viewport.d', 'shumate/MapSource.d', 'shumate/DataSource.d', 'shumate/SimpleMap.d', 'shumate/MapSourceRegistry.d', 'shumate/MarkerLayer.d', 'shumate/Tile.d', 'shumate/Compass.d', 'shumate/TileDownloader.d', 'shumate/Scale.d', 'shumate/LocationIF.d', 'shumate/MemoryCache.d', 'shumate/PathLayer.d', 'shumate/RasterRenderer.d', 'shumate/c/types.d', 'shumate/c/functions.d', 'shumate/c/types.d', 'shumate/c/functions.d']
)

shumate = library('shumate_d',
    sources: shumate_files,
    install: true,
    link_with: [gtk, linker, glib],
    version: meson.project_version(),
    soversion: linker_soversion,
)


pkg_shumate = import('pkgconfig')
pkg_shumate.generate(name: 'shumate_d',
               libraries: [shumate, glib, gtk, linker],
               version: meson.project_version(),
               description: 'Glib for gtk_d.',
               d_module_versions: ['2.68.1', 1]
)


install_subdir('linker', install_dir: 'include/d/gtk_d/')
install_subdir('glib', install_dir: 'include/d/gtk_d/')
install_subdir('gobject', install_dir: 'include/d/gtk_d/')
install_subdir('gthread', install_dir: 'include/d/gtk_d/')
install_subdir('graphene', install_dir: 'include/d/gtk_d/')
install_subdir('cairo', install_dir: 'include/d/gtk_d/')
install_subdir('harfbuzz', install_dir: 'include/d/gtk_d/')
install_subdir('pango', install_dir: 'include/d/gtk_d/')
install_subdir('gio', install_dir: 'include/d/gtk_d/')
install_subdir('gdkpixbuf', install_dir: 'include/d/gtk_d/')
install_subdir('atk', install_dir: 'include/d/gtk_d/')
install_subdir('gdk', install_dir: 'include/d/gtk_d/')
install_subdir('rsvg', install_dir: 'include/d/gtk_d/')
install_subdir('gsk', install_dir: 'include/d/gtk_d/')
install_subdir('gtk', install_dir: 'include/d/gtk_d/')
install_subdir('adw', install_dir: 'include/d/gtk_d/')
install_subdir('sourceview', install_dir: 'include/d/gtk_d/')
install_subdir('soup', install_dir: 'include/d/gtk_d/')
install_subdir('shumate', install_dir: 'include/d/gtk_d/')



